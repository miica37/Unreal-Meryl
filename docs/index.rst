.. Shenya Documentation master file, created by
	 sphinx-quickstart on Sat Sep  1 12:46:37 2018 (modifiend on March 2021).
	 You can adapt this file completely to your liking, but it should at least
	 contain the root `toctree` directive.

Meryl
=====

Some notes about the character Meryl on Unreal Engine Marketplace.


.. rst-class:: special
	For more images, please check out at this page `Shenya <https://rabbit-heart.my/portfolio/shenya/>`_

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

Non-Spherical Eyes
==================

Note that the eyes (and eyes shadow) is oval in shape.

.. image:: /images/non-spherical-eyes-01.jpg
	:align: center


.. image:: /images/non-spherical-eyes-02.jpg
	:align: center

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

The mesh is skinned to some extra bones:

.. image:: /images/bottoms-extra-bones2.jpg
	:align: center

I have also setup some physics box and capsules

.. image:: /images/bottoms-extra-bones3.jpg
	:align: center

I have created a simple blueprint setup to test the physics skirt:

BP_Meryl_Modular_EXB_Bottoms (EXB = Extra Bones)

.. image:: /images/bottoms-extra-bones-blueprint.jpg
	:align: center

Unfortunately, I couldn't get the setup to work properly at the moment so it is just there in case you need bones for the skirt.

.. image:: /images/physics-skirt-test.gif
	:align: center

|

Corrective Morph Targets
========================

If you need a pose for the character to sit down, there might be some issues because the skirt is very short and skinned to the thigh bones, it will looks akward and unnatural. 

With Cloth simulation ON:

.. image:: /images/sit1.jpg
	:align: center

Turn Off Cloth Simulation:

.. image:: /images/turn-off-cloth-simulation.jpg
	:align: center


.. image:: /images/sit2.jpg
	:align: center

I created a sit_corrective morph target to make it looks a bit better.

.. image:: /images/sit-corrective-morph-target.jpg
	:align: center

