
###############################
Meshes
###############################

Modularity
==========
Meryl V2 is updated with a new outfit and 3 new hairstyle, this allows for more combinations to be made:

.. image:: /images/meshes/map-preview2.jpg
	:align: center

.. image:: /images/meshes/map-preview1.jpg
	:align: center

LODs
====
Meryl V2 now has LOD1 (reduces tricount by about half).

Staff (SM_Staff_A) still doesn't have any lod.

In the demo scene (Meryl_Preview Map), if you choose between BP_Meryl1 or BP_Meryl2, you can press < 1 > to toggle between LOD0 and LOD1.

.. note::
	Creating LOD takes a lot of time so I am hoping to get some feedbacks from users to see which LOD they prefer. I would really appreciate if you could take some time to go into the `Discord server <https://discord.gg/WzspRd3QrG>`_ and vote on this subject.

Polycount
=========

+-----------------+------+-------------+
|Mesh Parts       |  LOD0|         LOD1|
+=================+======+=============+
|Head             | 10814|  5460 ( 50%)|
+-----------------+------+-------------+
|Body             | 19864|  9878 ( 49%)|
+-----------------+------+-------------+
|Eyes             |  1080|   520 ( 48%)|
+-----------------+------+-------------+
|Eyes_shadow      |   840|   360 ( 42%)|
+-----------------+------+-------------+
|Hair1            |  4823|  2408 ( 49%)|
+-----------------+------+-------------+
|Hair1_proxy      |   402|   402 (100%)|
+-----------------+------+-------------+
|Hair2            |  5950|  2932 ( 49%)|
+-----------------+------+-------------+
|Hair2_proxy      |   354|   354 (100%)|
+-----------------+------+-------------+
|Hair3            |  7235|  3581 ( 49%)|
+-----------------+------+-------------+
|Hair3_proxy      |   402|   402 (100%)|
+-----------------+------+-------------+
|Hair4            |  6586|  3388 ( 51%)|
+-----------------+------+-------------+
|Hair4_proxy      |   388|   388 (100%)|
+-----------------+------+-------------+
|Hat1             |  2154|  1054 ( 48%)|
+-----------------+------+-------------+
|Hat2             |  2082|  1035 ( 49%)|
+-----------------+------+-------------+
|Top1             |  8633|  4396 ( 50%)|
+-----------------+------+-------------+
|Top2             |  8036|  3821 ( 47%)|
+-----------------+------+-------------+
|Glove1           |  8040|  5062 ( 62%)|
+-----------------+------+-------------+
|Bloomers         |  1190|   617 ( 51%)|
+-----------------+------+-------------+
|Skirt1           |  8315|  3094 ( 37%)|
+-----------------+------+-------------+
|Skirt1_proxy     |   831|   831 (100%)|
+-----------------+------+-------------+
|Skirt2           |  3181|  1593 ( 50%)|
+-----------------+------+-------------+
|Skirt2_proxy     |  1020|   504 ( 49%)|
+-----------------+------+-------------+
|Leggings1        |  2580|  1180 ( 45%)|
+-----------------+------+-------------+
|Shoe1            |  3074|  1534 ( 49%)|
+-----------------+------+-------------+
|Boots1           |  4244|  2098 ( 49%)|
+-----------------+------+-------------+
|Hat1_static      |  2154|  1054 ( 48%)|
+-----------------+------+-------------+
|Hat2_static      |  2082|  1035 ( 49%)|
+-----------------+------+-------------+
|Flower1_static   |   380|   380 (100%)|
+-----------------+------+-------------+

|

.. note::
	I accidentally reduced Skirt1 a bit too much.

|

Meshes Overview
===============

SK_Meryl1 and SK_Meryl2
-----------------------

.. image:: /images/content-thumbnails/SK_Meryl.jpg
	:align: center

These are the precombined mesh, Meryl1 is wearing the first outfit while Meryl2 is wearing the new outfit.
The '1b' and '1c' are versions that has different material setups.

1
^
There are 13 material slots in this mesh. As you can see it's quite a lot of materials, and this will results in many draw calls.

.. image:: /images/meshes/meryl1-material-slots.jpg
	:align: center

1b
^^
The material slots is reduced to 8. This mesh is using the master clothes material which combines multiple material into one, the idea is to reduce material draw calls and you can read more about it here. The hair and skirt is not using the master clothes material (MI_Meryl_Clothes1) because they will need the material slots for clothing simulations.

.. image:: /images/meshes/meryl1b-material-slots.jpg
	:align: center


1c
^^
The material slots is reduced to 4. This is the minimum amount of material slots that you are able to reduce to. With this setup, there's will be no cloth simulations.

.. image:: /images/meshes/meryl1c-material-slots.jpg
	:align: center

.. note::
    A note on the eyes for 1c, it seems at first that I could merge the eyes into the master clothes material to reduce one more material slot, but somehow the eyes turns black when I did this, so I have to separate the eyes out.

    .. image:: /images/meshes/black-eyes.jpg
	    :align: center

|

Body and Clothes Parts
----------------------
You can mix and match the clothes parts inside the Blueprint.

.. image:: /images/meshes/meshes-thumbnails.jpg
	:align: center

.. image:: /images/meshes/blueprint-outline.jpg
	:align: center

|

About the Design
================

Non-Spherical Eyes
------------------

Note that the eyes (and eyes shadow) is oval in shape.

.. image:: /images/non-spherical-eyes-01.jpg
	:align: center

|

.. image:: /images/non-spherical-eyes-02.jpg
	:align: center

|

Eyes motion is driven through morph targets (instead of bones).

.. image:: /images/blendshapes-driven-eye-motion.jpg
	:align: center
