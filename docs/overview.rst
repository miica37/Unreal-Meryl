
Modularity
==========

Meryl is designed to be modular, in the latest update (:ref:`V2.0 <updates_v2>`), a new outfit and 3 new hairstyles are added which gives you more options to customize the character.

Due to designing to make it modular, please be aware that textures are separated into many different texture sets (eyes, head, body, top, skirt, leggings, boots, shoes, gloves, bloomers, etc) and this results in many materials instances used just for one character.

A technique was shared to me by a user (@Rashed) to create a master material that combines multiple materials into one in order to reduce the draw calls and therefore improve performance, which you can also use as an option for this character. :ref:`More info at the material section <clothes_master>`.

|

.. image:: /images/map-preview2.jpg
	:align: center

|

.. image:: /images/map-preview1.jpg
	:align: center

|

Features
========

* Follows UE4's Epic Skeleton (Mannequin)

* :ref:`LOD (Level of Details) <lods>`

* :ref:`Apple BlendShapes <blendshapes>`

* :ref:`Clothes <clothes>`

* :ref:`PBR Textures <textures>`

|

Skeleton
========

Meryl has a main skeleton :guilabel:`SK_Meryl_Skeleton`, the bones structure and naming are following UE4's Mannequin Skeleton exactly, while the bones position is adjusted to match my design of the character. The individual bones' orientation (their rotation axis) are closely matching the original Mannequin's bones orientation (second picture below show the bones orientation in Maya).

In short, unless you are going to animate Meryl yourself, you will need to :ref:`retarget the animations <retarget>`.

For ALS (`Advanced Locomotion System <https://www.unrealengine.com/marketplace/en-US/product/advanced-locomotion-system-v1#>`_), I had it working to some degree (please check out :ref:`my guide for ALS <als>`) however due to the difference in arm length, some work is required to fix the arms holding weapons.

.. image:: /images/skeleton.jpg
	:align: center

|

.. image:: /images/meryl-vs-mannequin-skeleton.jpg
	:align: center

|

Viewing Image
======================

The images of this documentation are automatically resized to fit the width of the contents area, some images actually have a higher resolution so you can try...

#. Right click on the image
#. Select "Open Image in New Tab"

to open the original image in another tab to see it better.

.. image:: /images/viewing-full-image-resolution.jpg
	:align: center

|
|

Authoring content and Exporting
===============================

Here's some tips if you would like to modify the mesh or animation in Maya or Blender.

Maya
----
Maya seems to be able to read the materials and blendshapes better than Blender so I recommend using Maya for authoring the mesh. I can also provide you with the source Maya file so the fbx you export out of Maya will be exactly like the one I bring into UE.

Blender
-------
I don't have much experience with Blender's skeleton and its workflow for bringing content into UE so the support that I can provide is going to be limited.

One of the issues one might face when exporting fbx out from UE and bringing it into Blender is the missing shape keys and material slots.

You can use `Fbx Converter <https://www.autodesk.com/developer-network/platform-technologies/fbx-converter-archives>`_ from Autodesk (`as pointed out by TheBasti82 in this Unreal Engine forum thread <https://forums.unrealengine.com/t/export-shape-keys-morph-targets-from-ue4-to-blender-workaround/133040>`_) to convert the fbx files (from UE) before importing them into Blender to solve the issue.

The original fbx files (that I use to bring mesh and skeleton into UE) will be provided on request and it will also solve the above issue.

|
|

Unreal Engine 5
===============

.. image:: /images/ue5/ue5-viewport.jpg
    :align: center

Meryl has been tested briefly on UE5 and seems to be working fine. However I was working mostly on UE 4.22 so if there are any issues with other UE versions, please report back and I will try to fix them ASAP.

One thing I noticed when opening the preview map in UE5 (and also UE4.27) is it looks much brighter than the same map in UE4. The exposure compensation setting for PostProcessVolume has reverted back to 1.0, so turning it back to 0.0 should line up the looks with UE 4.22. 

.. image:: /images/ue5/ue5-after.jpg
    :align: center

|

.. note::
    :ref:`Retargeting Guide for UE5 <retarget_ue5>`

|
|

Supports
========

📧 Email
---------
You can post Questions at Unreal Marketplace or send me an email: miicaneo@gmail.com and I will try to reply to you as soon as I can.


.. Discord
   -------
    I also created a Discord Server as another option:

    https://discord.gg/WzspRd3QrG

    .. Note::
        The Discord setup is very simple for now as I don't have much experience with Discord.

|
