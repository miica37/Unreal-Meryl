
###############################
Animations
###############################

.. role:: folder

Locations
=========

In order to differentiate between original animations and retargeted animations, animations are located in two different folders. Original Animations are inside :folder:`Animations` folder while Retargeted Animations are inside :folder:`Demo` folder.

In fact, since there are almost no original animations (besides a facial morph target animation :guilabel:`Anim_smile_blink`), you will find **most** of the animation in the :folder:`Demo` folder. This folder contains a few animations retargeted from UE4 Mannequin, Paragon's Yin and Windwalker Echo.

Among the retargeted animations: :guilabel:`Anim_Echo_Idle_Long`, :guilabel:`Anim_Echo_Walk_Fwd` and :guilabel:`Anim_Yin_Idle_Combat2` have some slight modifications in Maya.

|

.. _retarget:

Retargeting Animations
======================

Since Meryl's skeleton is a different proportion than UE4 skeleton which most animation in the marketplace is based on, you will have to retarget the animations to Meryl.

Documentation:
   You can read more about retargeting for UE4 at the official `Unreal Engine 4.27 Documentation - Animation Retargeting <https://docs.unrealengine.com/4.27/en-US/AnimatingObjects/SkeletalMeshAnimation/AnimationRetargeting/>`_, and UE5 at `Unreal Engine 5.0 Documentation - IK Rig Retargeting <https://docs.unrealengine.com/5.0/en-US/ik-rig-animation-retargeting-in-unreal-engine/>`_.

Below is some step by step instructions:

|

Unreal Engine 4
---------------

.. note::
	Step by Step Video at Youtube:
		`Animation Retargeting in UE4 // Meryl <https://www.youtube.com/watch?v=EqlSjc5xunU>`_

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
|

.. _retarget_ue5:

Unreal Engine 5
---------------

UE5 has a different workflow for retargeting. First an IK Rig needs to be created for the character but don't worry I have already setup and prepared the IK Rig which you can get at `this link <http://link>`_.

.. note::
	Step by Step Video at Youtube:
		`Animation Retargeting in UE5 // Meryl <https://www.youtube.com/watch?v=JUodYLNm-b4>`_


Create IK Retargeter
^^^^^^^^^^^^^^^^^^^^

   #. Copy both < IK_Meryl > and < SK_Meryl2_UE5 > to folder :folder:`Meryl ➧ Meshes`

      .. image:: /images/animations/retarget-ue5-copy-asset.jpg
		:align: center

   #. Go to folder :folder:`Characters ➧ Mannequins ➧ Rigs`,
     
	  Duplicate < RTG_Mannequin > and name it < RTG_Meryl_to_UE5 > 

	  .. image:: /images/animations/retarget-ue5-duplicate-retargeter.jpg
		:align: center

   #. Open < RTG_Meryl_to_UE5 >
     
	  Set the **Target IKRig** to < IK_Meryl > and **Target Preview Mesh** to < SK_Meryl2_UE5 >

	  .. image:: /images/animations/retarget-ue5-set-target-ikrig.jpg
		:align: center

      |

	  In the **Chain Mapping** panel, select **LeftArm**, **RightArm**, **LeftLeg**, **RightLeg** and turn Off the **Drive IKGoal** setting for all of them

	  .. image:: /images/animations/retarget-ue5-turn-off-drive-ikgoal.jpg
		:align: center

   #. Switch to **Asset Browser** panel and play some animations to check if everything looks alright

|

Duplicate Animation Blueprint
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

   #. Go to folder :folder:`Characters ➧ Mannequins ➧ Animations`,

      Right click on < ABP_Quinn > and select **Retarget Animation Assets ➧ Duplicate and Retarget Animation Blueprint**

	  .. image:: /images/animations/retarget-ue5-retarget-animbp.jpg
		:align: center

   #. In the "Duplicate and Retarget Animation Blueprint" Window,

      Set IK Retargeter to < RTG_Meryl_to_UE5 >

      Set Search "Quinn" and Replace "Meryl"

      Set the output Folder to :folder:`Meryl ➧ Demo`

	  .. image:: /images/animations/retarget-ue5-retarget-animbp-window.jpg
		:align: center
	
	  |

      Hit the "Retarget" Button. You will find the retargeted animations and anim blueprint at the folder you set above.

|

Duplicate Character Blueprint
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

   #. Go to folder :folder:`ThirdPerson ➧ Blueprints`,

      Duplicate < BP_ThirdPersonCharacter > and name it < BP_Meryl_UE5 >

	  .. image:: /images/animations/retarget-ue5-duplicate-bp.jpg
		:align: center

   #. Open the blueprint < BP_Meryl_UE5 >,

      Change the mesh to < SK_Meryl2 > and set the animation blueprint to < ABP_Meryl >

	  .. image:: /images/animations/retarget-ue5-edit-bp.jpg
		:align: center

   #. Compile and Save

|

Set Player
^^^^^^^^^^

   #. In the World Settings, under **Game Mode ➧ Selected GameMode**,

      Set **Default Pawn Class** to < BP_Meryl_UE5 > (created from the step above)

	  .. image:: /images/animations/retarget-ue5-world-settings.jpg
		:align: center

   #. Play the game to see the retargeted character.

      .. image:: /images/animations/retarget-ue5-done.jpg
		:align: center

|