
###############################
Dynamic Bones
###############################


Dynamic Folders
===============
Inside the < Meshes > folder, there are subfolders named < xxxxx_Dynamic >. These are some meshes with their own set of skeletons that contains extra bones for dynamic simulation.

The folder also contains a very simple animation blueprint. The animation blueprint is used inside BP_Meryl_Modular_xxxxx_Dynamics blueprint so the main bones (head or pelvis bones) are following the main skeleton. The technique is described in UE's Documentation: `Working with Modular Characters <https://docs.unrealengine.com/4.27/en-US/AnimatingObjects/SkeletalMeshAnimation/WorkingwithModularCharacters/>`_

.. image:: /images/dynamics/skirt1-dynamic-folder.png
	:align: center

|

Skirt1 is skinned to some extra bones:

.. image:: /images/dynamics/bottoms-extra-bones2.jpg
	:align: center

|

Physics Asset setup:

.. image:: /images/dynamics/bottoms-extra-bones3.jpg
	:align: center

|

I have created a simple blueprint setup to test the physics skirt and hair4:

.. image:: /images/dynamics/dynamic-bones-blueprints.jpg
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
