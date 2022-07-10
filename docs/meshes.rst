
###############################
Meshes
###############################

.. role:: folder

.. _lods:

LODs
====
Meryl V2 now has LOD1 (reduces tricount by about half).

Staff (SM_Staff_A) still doesn't have any lod.

In the demo scene (Meryl_Preview Map), if you choose between BP_Meryl1 or BP_Meryl2, you can press < 1 > to toggle between LOD0 and LOD1.

.. note::
	Creating LOD takes a considerable amount of time, based on my :ref:`performance test <performance>`, the performance increase from lod is negligible.

	As hardware continues to improve and Unreal Engine shifts to high end technologies like Lumen and Nanite, I believe creating LOD is slowly becoming a thing of the past.

	With that said, I will remove LOD in the future updates, do let me know (miicaneo@gmail.com) if you have other considerations.

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

.. _meshes_overview:

Meshes Overview
===============

SK_Meryl1 and SK_Meryl2
-----------------------

.. image:: /images/SK_Meryl.jpg
	:align: center

These are the precombined mesh, :guilabel:`Meryl1` is the first design while :guilabel:`Meryl2` is having the new outfit.

The :guilabel:`b` and :guilabel:`c` are variations that have reduced material slots and the material setup to use < M_Meryl_Clothes_Master > (:ref:`link <clothes_master>`).

Meryl 1
^^^^^^^

There are 13 material slots in this mesh. As you can see it's quite a lot of materials, and this can have an impact on performance.

.. image:: /images/meshes/meryl1-material-slots.jpg
	:align: center

|

Meryl 1b
^^^^^^^^

The amount of material slots is reduced to 8. This skeletal mesh is using a master clothes material which combines multiple materials, so we can use the same material for the top, leggings, boots and hat.

For hair and skirt, they will still be occupying 4 material slots (one for the primary mesh and one for proxy mesh for each) because for clothing simulations, material slots are used to select the clothing.


.. image:: /images/meshes/meryl1b-material-slots.jpg
	:align: center

|

.. image:: /images/meshes/meryl1b-clothing-slots.jpg
	:align: center

|

Meryl 1c
^^^^^^^^

The amount of material slots is reduced to 4. This is the minimum amount of material slots that you are able to reduce (unless you want to remove the eyes shadow too which doesn't look too good closeup). With this setup, we will have to give up cloth simulations.

.. image:: /images/meshes/meryl1c-material-slots.jpg
	:align: center

.. note::
    A note on the eyes for 1c, it seems at first that we can also merge the eyes into the master clothes material to reduce one more material slot, but somehow the eyes turned black when I did this, so I had to separate the eyes out.

    .. image:: /images/meshes/black-eyes.jpg
	    :align: center

|
|

Body and Clothes Parts
----------------------

.. image:: /images/meshes/meshes-thumbnails.jpg
	:align: center

|

To customize the look, you can use these mesh parts and mix and match them inside the Blueprint.

You can take a look at :guilabel:`BP_Meryl_Modular` in the :folder:`Blueprints` folder to see how it's setup, which you can also learn more about in the UE's Documentation: `Working with Modular Characters <https://docs.unrealengine.com/4.27/en-US/AnimatingObjects/SkeletalMeshAnimation/WorkingwithModularCharacters/>`_

|

.. image:: /images/meshes/blueprint-outline.jpg
	:align: center

|
|

.. _clothes:

Clothing Simulation
===================

The Hairs and Skirts are setup to work with clothing simulation using proxy meshes, which means there is a separate mesh that has a lower mesh resolution that is driving the primary mesh.

The proxy mesh has "proxy" in its name. :guilabel:`Hair1`'s (the primary mesh) proxy is :guilabel:`Hair1_Proxy`.

In the LOD section, you can find that the proxy mesh is set to disabled (but when you Activate Cloth Paint, you will be painting on the proxy mesh):

.. image:: /images/meshes/clothing-material-slot.jpg
	:align: center

|
|

About the Design
================

Non-Spherical Eyes
------------------

Just a note that the eyes (and eyes shadow) is oval in shape.

.. image:: /images/non-spherical-eyes-01.jpg
	:align: center

|

.. image:: /images/non-spherical-eyes-02.jpg
	:align: center

|

Eyes motion is driven through morph targets (instead of bones).

.. image:: /images/blendshapes-driven-eye-motion.jpg
	:align: center

|
