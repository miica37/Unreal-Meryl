.. Shenya Documentation master file, created by
	 sphinx-quickstart on Sat Sep  1 12:46:37 2018 (modifiend on March 2021).
	 You can adapt this file completely to your liking, but it should at least
	 contain the root `toctree` directive.

Meryl
=====

Some notes about the character Meryl on Unreal Engine Marketplace.

.. image:: /images/Meryl-cover.jpg
	:align: center

|

Polycount
=========

+---------------+-------+
| Model Parts   | Tris  |
+===============+=======+
| Head          | 10814 |
+---------------+-------+
| Body          | 19864 |
+---------------+-------+
| Hat           | 2154  |
+---------------+-------+
| Hairs         | 4827  |
+---------------+-------+
| Tops          | 8921  |
+---------------+-------+
| Bottoms       | 8315  |
+---------------+-------+
| Leggings      | 2580  |
+---------------+-------+
| Boots         | 4244  |
+---------------+-------+
| Eyes          | 1080  |
+---------------+-------+
| Eyes Shadow   | 1080  |
+---------------+-------+
| Underwear     | 574   |
+---------------+-------+
| ---Total---   | 64453 |
+---------------+-------+

|

Retargeting Animations
======================

Short Video Demonstration\: `Animation Retargeting in UE4 - Using Meryl as Example <https://www.youtube.com/watch?v=EqlSjc5xunU>`_ (Youtube)

Step1: 

 - Select the animations that you want to retarget from
 
 - Right click on them and choose *Retarget Anim Assets -> Duplicate Anim Assets and Retarget*

.. image:: /images/retarget-step1.jpg
	:align: center

|

Step2: 

 - In the "Select Skeleton" pop up Window...
 
 - Uncheck "Show Only Compatible Skeletons"
 
 - Select SK_Meryl_Skeleton
 
 - Change the output location if you want

 - Click on Retarget.

.. image:: /images/retarget-step2.jpg
	:align: center

|

Non-Spherical Eyes
==================

Note that the eyes (and eyes shadow) is oval in shape.

.. image:: /images/non-spherical-eyes-01.jpg
	:align: center

|

.. image:: /images/non-spherical-eyes-02.jpg
	:align: center

|

Eyes motion can be driven through morph targets in Unreal Engine.

.. image:: /images/blendshapes-driven-eye-motion.jpg
	:align: center

|

Bottoms Extra Bones Folder
==========================

Naming explaination: `Tops` means cloths at the top (ie. shirt, etc) and `Bottoms` means cloths at the bottom (ie. skirt, pants, etc).

(EXB = Extra Bones)

The default bottoms mesh in the Meshes folder (SK_Meryl_Bottoms) is skinned to the pelvis and thigh joints, but I also provide an extra bottoms mesh (SK_Meryl_EXB_Bottoms) that are skinned to extra skirt bones (which uses a separate skeleton).

The folder "BottomsExtraBones" contains mesh, skeleton, physic asset and animation blueprint for the alternate bottoms mesh.

.. image:: /images/bottoms-extra-bones.jpg
	:align: center

|

The mesh is skinned to some extra bones:

.. image:: /images/bottoms-extra-bones2.jpg
	:align: center

|

I have also setup some physics box and capsules

.. image:: /images/bottoms-extra-bones3.jpg
	:align: center

|

I have created a simple blueprint setup to test the physics skirt:

BP_Meryl_Modular_EXB_Bottoms (EXB = Extra Bones)

.. image:: /images/bottoms-extra-bones-blueprint.jpg
	:align: center

|

Unfortunately, I couldn't get the setup to work properly at the moment so it is just there in case you need bones for the skirt.

.. image:: /images/physics-skirt-test.gif
	:align: center

|

List of Extra Bones for the alternate Skeleton
==============================================

* Note that the main skeleton doesn't have any extra bones, this is an alternate skeleton for the bottoms mesh.


.. image:: /images/bottoms-extra-bones-list.jpg
	:align: center

|

* skirtFront_01_l, skirtFront_02_l, skirtFront_03_l
* skirtFront_01_r, skirtFront_02_r, skirtFront_03_r
* skirtSide_01_l, skirtSide_02_l, skirtSide_03_l
* skirtSide_01_r, skirtSide_02_r, skirtSide_03_r
* skirtBack_01_l, skirtBack_02_l, skirtBack_03_l
* skirtBack_01_r, skirtBack_02_r, skirtBack_03_r
* skirtBetwFront_01_l, skirtBetwFront_02_l, skirtBetwFront_03_l
* skirtBetwFront_01_r, skirtBetwFront_02_r, skirtBetwFront_03_r
* skirtBetwBack_01_l, skirtBetwBack_02_l, skirtBetwBack_03_l
* skirtBetwBack_01_r, skirtBetwBack_02_r, skirtBetwBack_03_r

|

Corrective Morph Targets
========================
If you need a pose for the character to sit down, there might be some issues because the skirt is very short and skinned to the thigh bones, it will looks akward and unnatural. 

With Cloth simulation ON:

.. image:: /images/sit1.jpg
	:align: center

|

Turn Off Cloth Simulation:

.. image:: /images/turn-off-cloth-simulation.jpg
	:align: center

|

.. image:: /images/sit2.jpg
	:align: center

|

I created a sit_corrective morph target to make it looks a bit better.

.. image:: /images/sit-corrective-morph-target.jpg
	:align: center

|

Updates Log
===========

1.04 (07/06/2022)
--------------------

 * Fix incorrect position of IK bones

|


1.03 (11/04/2022)
--------------------

 * Fix (improved slightly) Physics Asset (SK_Meryl_PhysicsAsset)

 * Eyes color adjustable (Added T_Meryl_Eyes_Mask, and Updated M_Eyes_Master)

.. image:: /images/changelog/v1.03/adjustable-eyes-color.gif
	:align: center

|


1.02 (09/03/2022)
--------------------

 * Fix Animation: Anim_smile_blink

 * Added new skeletal mesh: SK_Meryl_no_hat

|

1.01 (07/03/2022)
--------------------

 * Fix missing blendshapes in SK_Meryl_Head
