
###############################
Materials
###############################

.. role:: material

Overviews
=========
The < Materials > folder contains master materials (inside subfolder < Master >) and material instances. Master materials are named M_xxxxx_Master (or just M_xxxxx if it wasn't going to be instanced) while material instances are named MI_xxxxx.

.. image:: /images/materials/materials-thumbnails.jpg
	:align: center

|

Master Materials
================

:material:`M_Generic_Master`
----------------------------
The most simple PBR material, limited to 3 textures input (Base Color, Normal and MRAO), and a parameter to control its specular value.

|

:material:`M_Generic_Tint_Master`
---------------------------------
An upgraded version of :material:`M_Generic_Master` that accepts a RGB texture as input to change the color of diffuse texture.

The `Power` parameters is used to adjust the brightness (or darkness) of the color.

This base material is commonly used in many material instances.

.. image:: /images/materials/M_Generic_Tint_Master-example.jpg
	:align: center

|

:material:`M_Generic_Tint_Glow_Master`
--------------------------------------
Base on :material:`M_Generic_Tint_Master` with a glow component. Requires an Emissive Mask Texture. Only used by some Hat1 material instances because there's only one emissive mask texture (T_Meryl_Hat1_E).

|

:material:`M_Generic_Vert_Offset_Master`
----------------------------------------
Based on :material:`M_Generic_Master` with added ability to offset vertex position on Skirt2, to solve mesh intersections between Skirt2 and Legs while the character runs for example.

Skirt2 has a gradient vertex colors and vertices with brighter color will push out more.

.. image:: /images/materials/skirt2-vertex-color.jpg
	:align: center

|

:material:`M_Generic_Tint_Vert_Offset_Master`
---------------------------------------------
Based on :material:`M_Generic_Tint_Master`, and just like :material:`M_Generic_Vert_Offset_Master`, it has added ability to offset vertex position based on vertex color.

.. note::
	Both the Vert Offset materials can only used by Skirt2 because most other meshes don't have the vertex colors to work with it.

|

:material:`M_Generic_Tint_Cutout_Master`
----------------------------------------
A material initially created to masked out mesh sections. The idea is to use vertex colors to assign colors to different part of the mesh, then the color will be read as mask inside this material to make them transparent. There are just a few meshes with vertex colors, and only two that you can use this material with: Top1 and Hair4.

With this material, you can cutout the glove from Top1, or cutout the ponytail from Hair4 (when wearing a hat).

This material is limited to use only 3 vertex colors which is Red, Green and Blue.

.. image:: /images/materials/mesh-with-vertex-colors.jpg
	:align: center

.. note::
    Body material use a different method to do masking below

|

:material:`M_Meryl_Fullbody_Master`
-----------------------------------

.. image:: /images/materials/MI_Meryl_Fullbody-parameters.jpg
	:align: center

.. image:: /images/materials/MI_Meryl_Fullbody-material-example.jpg
	:align: center


