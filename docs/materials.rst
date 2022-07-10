
###############################
Materials
###############################

.. role:: folder
.. role:: material
.. role:: material2

Overviews
=========
The :folder:`Materials` folder contains master materials and material instances. Master materials are named [ M_xxxxx_Master ] and Material instances are named [ MI_xxxxx ]. Some materials that are not going to be instanced are named [ M_xxxxx ] (eg. [ M_Eyes_Shadow ] ).

.. image:: /images/materials/content-materials-thumbnails.jpg
	:align: center

|
|

Master Materials
================
[ M_xxxxx_Master ] are located inside the subfolder :folder:`Master`.


List of Master Materials:

.. image:: /images/materials/content-master-materials.jpg
	:align: center

|

Eyes Masters
------------

.. image:: /images/materials/content-eyes-master-material-highlight.jpg
	:align: center

|

:material:`M_Eyes_Master`
^^^^^^^^^^^^^^^^^^^^^^^^^

Basic eye material with ability to change eye colors.

.. image:: /images/materials/mi-meryl-eyes-parameters.jpg
	:align: center

|

.. _duo_eyes:

:material:`M_Duo_Eyes_Master`
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Based on [ M_Eyes_Master ], with added ability to give left eye and right eye two different colors.

The eye's mesh has vertex colors (one color for the left eye and another color for the right eye), which is converted into masking inside the material to give both sides different colors.

.. image:: /images/materials/mi-meryl-duo-eyes-preview.jpg
	:align: center

|

.. image:: /images/materials/mi-meryl-duo-eyes-parameters.jpg
	:align: center

|

Generic Masters
---------------

.. image:: /images/materials/content-generic-master-material-highlight.jpg
	:align: center

|

:material:`M_Generic_Master`
^^^^^^^^^^^^^^^^^^^^^^^^^^^^
A very basic PBR material, with just 3 textures input (Base Color, Normal and MRAO), and a parameter to control its specular value.

.. image:: /images/materials/m-generic-master-parameters.jpg
	:align: center

|

:material:`M_Generic_Tint_Master` (Commonly Used)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
An upgraded version of [ M_Generic_Master ] that accepts a RGB texture as input to change the color of diffuse texture.

`Power` Parameter:
	The `Power` parameter setting is used to adjust the brightness (or darkness) of the color.

.. image:: /images/materials/M_Generic_Tint_Master-example.jpg
	:align: center

|

:material:`M_Generic_Tint_Glow_Master`
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Based on [ M_Generic_Tint_Master ] with a glow component. Requires an Emissive Mask Texture. Only used by some Hat1 material instances because there's only one emissive mask texture ( < T_Meryl_Hat1_E > ).

|

:material:`M_Generic_Vert_Offset_Master`
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Based on [ M_Generic_Master ] with added ability to offset vertex position on Skirt2, to solve mesh intersections between Skirt2 and Legs while the character runs for example.

Skirt2 has vertex colors on it, and is painted in a gradient. Vertices on top with darker values will not be pushed as much as the vertex at the bottom.

.. image:: /images/materials/skirt2-vertex-color.jpg
	:align: center

|

:material:`M_Generic_Tint_Vert_Offset_Master`
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Based on [ M_Generic_Tint_Master ] , and just like [ M_Generic_Vert_Offset_Master ], it has added ability to offset vertex position based on vertex color.

.. note::
	Both the Vert Offset materials can only used by Skirt2 because most other meshes doesn't have any vertex colors data to work with it.

|

:material:`M_Generic_Tint_Cutout_Master`
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
A material initially created to mask out mesh sections. The idea is to use vertex colors to assign colors to different parts of the mesh, then the color will be read as a mask inside this material to make them transparent. There are just a few meshes with vertex colors, and only two that you can use this material with: < Top1 > and < Hair4 >.

With this material, you can cut out the glove from < Top1 >, or cut out the ponytail from < Hair4 > (when wearing a hat).

This material is limited to 3 vertex colors that can be used which are Red, Green and Blue.

.. image:: /images/materials/mesh-with-vertex-colors.jpg
	:align: center

|

.. note::
    Body material does not use vertex colors to do masking. It uses a second UV channel to store the different sections (:ref:`explained below <body_masking>`).

|
|

.. _clothes_master:

Clothes Master
--------------

.. image:: /images/materials/content-clothes-master-material-highlight.jpg
	:align: center

:material:`M_Meryl_Clothes_Master`
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

[ M_Meryl_Clothes_Master ] is used on < Mery 1b > and < Meryl 1c >. More info :ref:`here <meshes_overview>`.

Material instances of this master material are located under :folder:`Meryl\\Materials\\Clothes`.

This master material is used to improve rendering performance. The default < SK_Meryl1 > skeletal mesh has many material instances, this material merges the cloth (and hair) materials into one material.

.. warning::
	Cons:
		When using the material instance of master clothes material, the shader compilation time is much longer, for example, if you enable some checkbox like say "Use Hair Color1", it will trigger the shader to compile and on my old PC, I will have to wait a while before it finishes update and only then can I start tweaking the color.
		
		This might be just a one time thing though...

.. attention::
	Using it in a modular Blueprint:
		In order to get the performance benefit, *I believe* you need to do merge the meshes (see the UE's Documentation: `Working with Modular Characters <https://docs.unrealengine.com/4.27/en-US/AnimatingObjects/SkeletalMeshAnimation/WorkingwithModularCharacters/>`_ Skeletal Mesh Merge section), because if you assemble the skeletal meshes in Blueprint using multiple Skeletal Mesh components, each of them are still going to create separate draw calls even if all of them using the same material.

		**Meryl doesn't come with Mesh Merge** (I still have yet to learn how to use this).

Explaining The Concept
^^^^^^^^^^^^^^^^^^^^^^

[ M_Meryl_Clothes_Master ] is a material that combines multiple materials into one single master material. The idea comes from a user (Rashed) who shared with me the video `Reducing Draw Calls in Unreal! by PrismaticaDev <https://www.youtube.com/watch?v=ncwW5KNQ1Eg>`_.

From the Video Description:
	*Today we're looking at my current system for creating complex, modular, detailed, multi-textured objects without incurring extra draw calls. This system is quite easy to use once you wrap your head around it, and is a great way to convert existing multi-material assets into a unified material setup! Your GPU will thank you, and your artists will as well.*

To explain it the best I can, first we need to create a second uv channel for all the mesh parts that we want to use inside the master material. For each mesh part, we scale down the second uv and move it into one of the sections. In the UE Material, we split the uv horizontally into sections which look something like the image below, except they are not in color but black and white (and white only on one section, the rest is black). Then we are able to select any section based on the previous black and white mask and use the mask on the textures.

For example, we have a mesh with combined hair, skirt and boots. If we use a normal material and apply the hair textures onto the mesh, the hair textures will appear in all hair, skirt and boots. But by using the second uv channel, we are able to create a mask that targets the hair section, and have the hair textures to only show up only on the hair. The skirt and boots will appear black. We then do the same masking method for the skirt and boots, and at the last step we use the "Add" node to merge all the textures.

.. image:: /images/materials/clothes-uv2.jpg
	:align: center

.. note::
   Bloomers is assigned to Accessory1 section.

The image below shows the mesh sections. You can compare their colors with the uv sections image above to see which section each mesh belongs to.

.. image:: /images/materials/clothes-material-id.jpg
	:align: center

|

:material:`MF_Get_Material_ID_Mask`
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

This is a **Material Function** and it is being used inside [ M_Meryl_Clothes_Master ] and [ M_Meryl_Fullbody_Master ], it accepts an integer as an input to specify which section to use for masking, and outputs a black and white mask like the image below. The number of sections that this function assumes is hardcoded to 16 sections. 

Note that the input integer is based from zero, so to select the first section, use 0 (instead of 1) as the input.

For the image below, the white area represents the 6th section, out of 16 sections. 

.. image:: /images/materials/bnw-horizontal-split-16.jpg
	:align: center

|
|

Skin Master
-----------

.. image:: /images/materials/content-skin-master-material-highlight.jpg
	:align: center

:material:`M_Meryl_Fullbody_Master`
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
[ M_Meryl_Fullbody_Master ] is the updated skin material (from V1) which has the benefit of 1. reduced draw calls and 2. let you modify both the head and body material parameters in one place and 3. the ability to hide different sections of the mesh.

That function of hiding sections of the mesh is used mainly to solve body mesh intersecting with the clothes, either due to poor skin weights, extreme movements or sometimes it just inevitably happens regardless of how good the skin weight is.

.. image:: /images/materials/MI_Meryl_Fullbody-parameters.jpg
	:align: center

|

.. image:: /images/materials/MI_Meryl_Fullbody-material-example.jpg
	:align: center

|

.. _body_masking:

How Body Masking Works
^^^^^^^^^^^^^^^^^^^^^^

[ M_Meryl_Fullbody_Master ] is based on the same concept as [ M_Meryl_Clothes_Master ] above. Similar to the clothes meshes, the whole body is splitted up into smaller sections under the second uv channel.

[ MF_Get_Material_ID_Mask ] is then used to create the masking and the result plugged into the Opacity Mask of the material.

.. image:: /images/materials/body-uv2.jpg
	:align: center

|

.. image:: /images/materials/body-material-id.jpg
	:align: center

|
|

Other Materials
===============

.. image:: /images/materials/other-materials.jpg
	:align: center

|

Wireframe Materials
-------------------
[ M_Wireframe ] and its instance [ MI_Wireframe ] is used only in the Preview map to show the wireframe.

:material:`M_Transparent`
-------------------------
[ M_Transparent ] is used on the material slots of :ref:`cloth proxy meshes <clothes>`.

:material:`M_Eyes_Shadow`
-------------------------
Meryl eyes has an additional mesh layer that covers the eyes (with slight offsets) to add an additional layer of painted shadow to the eye.

The eye shadow mesh covering the eyes is using [ M_Eyes_Shadow ].

Old Skin Materials
------------------
[ M_Meryl_Head ] and [ M_Meryl_Body ] are the first implementation of the skin materials. They are now superseded by [ M_Meryl_Fullbody_Master ].

You can safely ignore [ M_Meryl_Body_Cutout ].

|
