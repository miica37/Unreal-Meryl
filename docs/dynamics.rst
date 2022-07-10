
###############################
Dynamic Bones
###############################

.. role:: folder

.. _dynamics:

Dynamic Folders
===============

.. image:: /images/dynamics/skirt1-dynamic-folder.jpg
	:align: center

Inside the :folder:`Meryl\\Meshes\\xxxxx_Dynamic` subfolders are meshes with their special skeletons that have extra bones for dynamic simulation.

The folder also contains a simple animation blueprint which is used by < BP_Meryl_Modular_xxxxx_Dynamics > (:ref:`character blueprints <content_dynamics_blueprints>`) from the :folder:`Meryl\\Blueprints` folder, following techniques as described in UE's Documentation: `Working with Modular Characters <https://docs.unrealengine.com/4.27/en-US/AnimatingObjects/SkeletalMeshAnimation/WorkingwithModularCharacters/>`_

.. note::
	These dynamic assets are work in progress, in the future I will test with skeletons that don't include body skeleton, so you can combine for example the extra hair bones with the extra skirt bones.

	For now, the setup I have is very unstable and not very usable which is why I resort to cloth simulation.

	The development for this is also lacking but I will study this more to provide a better solution, any help will be great and much appreciated.

|

Skirt1 is skinned to some extra bones:

.. image:: /images/dynamics/bottoms-extra-bones2.jpg
	:align: center

|

Physics Asset setup:

.. image:: /images/dynamics/bottoms-extra-bones3.jpg
	:align: center

|

.. _content_dynamics_blueprints:

I have created a simple blueprint setup to test the physics skirt and hair4:

.. image:: /images/dynamics/content-dynamic-blueprints.jpg
	:align: center

|

Unfortunately, I couldn't get the setup to work properly at the moment so it is just there in case you need bones for the skirt.

.. image:: /images/dynamics/physics-skirt-test.gif
	:align: center

|

List of Extra Bones
===================

Skirt1_Dynamic
--------------

.. admonition:: Target List
	:class: refbox

	:Skirt1: * skirtFront_01_l, skirtFront_02_l, skirtFront_03_l
            * skirtFront_01_r, skirtFront_02_r, skirtFront_03_r
            * skirtSide_01_l, skirtSide_02_l, skirtSide_03_l
            * skirtSide_01_r, skirtSide_02_r, skirtSide_03_r
            * skirtBack_01_l, skirtBack_02_l, skirtBack_03_l
            * skirtBack_01_r, skirtBack_02_r, skirtBack_03_r
            * skirtBetwFront_01_l, skirtBetwFront_02_l, skirtBetwFront_03_l
            * skirtBetwFront_01_r, skirtBetwFront_02_r, skirtBetwFront_03_r
            * skirtBetwBack_01_l, skirtBetwBack_02_l, skirtBetwBack_03_l
            * skirtBetwBack_01_r, skirtBetwBack_02_r, skirtBetwBack_03_r


.. image:: /images/dynamics/skirt1-extra-bones-list.jpg
	:align: center

|

Hair4_Dynamic
-------------

.. admonition:: Target List
	:class: refbox

	:Hair4: hair_01, hair_02, hair_03, hair_04, hair_05, hair_06, hair_07, hair_08, hair_09

.. image:: /images/dynamics/hair4-extra-bones-list.jpg
	:align: center

|
