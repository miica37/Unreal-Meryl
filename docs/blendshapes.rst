
.. role:: folder

.. _blendshapes:

###############################
Morph Targets (or Blendshapes)
###############################

Meshes
======

A few meshes have morph targets: :guilabel:`Head`, :guilabel:`Eyes` (part of Head), :guilabel:`Bloomers` and :guilabel:`Skirt1`

Head
----

The Head has about 55 morph targets that are created by following the guide on `Apple's ARKit documentation <https://developer.apple.com/documentation/arkit/arfaceanchor/blendshapelocation/>`_. It should work with Unreal's Live Link Face.

.. image:: /images/blendshapes/blendshapes-preview.jpg
	:align: center

.. admonition:: Target List
	:class: refbox

	:Eyes: eyeBlinkLeft
            eyeBlinkRight
            eyeLookDownLeft
            eyeLookDownRight
            eyeLookInLeft
            eyeLookInRight
            eyeLookOutLeft
            eyeLookOutRight
            eyeLookUpLeft
            eyeLookUpRight
            eyeSquintLeft
            eyeSquintRight
            eyeWideLeft
            eyeWideRight
	:Jaw: jawForward
            jawLeft
            jawRight
            jawOpen
	:Mouth: mouthClose
            mouthFunnel
            mouthPucker
            mouthLeft
            mouthRight
            mouthSmileLeft
            mouthSmileRight
            mouthFrownLeft
            mouthFrownRight
            mouthDimpleLeft
            mouthDimpleRight
            mouthStretchLeft
            mouthStretchRight
            mouthRollLower
            mouthRollUpper
            mouthShrugUpper
            mouthShrugLower
            mouthPressLeft
            mouthPressRight
            mouthLowerDownLeft
            mouthLowerDownRight
            mouthUpperUpLeft
            mouthUpperUpRight
	:Brow: browDownLeft
            browDownRight
            browInnerUp
            browOuterUpLeft
            browOuterUpRight
	:Cheek: cheekPuff
            cheekSquintLeft
            cheekSquintRight
	:Nose: noseSneerLeft
            noseSneerRight
	:Etc: tongueOut
            mouthNarrow
            lipsSeal
            lipsPart
            lowerTeethUp
            tongueTipUp

Eyes
----

Eyes morph together with the eyelids (which is part of the Head), the following morph targets will move the eyes.

.. admonition:: Target List
	:class: refbox

	:Eyes: eyeBlinkLeft
            eyeBlinkRight
            eyeLookDownLeft
            eyeLookDownRight
            eyeLookInLeft
            eyeLookInRight
            eyeLookOutLeft
            eyeLookOutRight
            eyeLookUpLeft
            eyeLookUpRight
            eyeWideLeft
            eyeWideRight

Bloomers
--------
To prevent Bloomers mesh from intersecting with the skirt, it is modeled to tightly fit the skin but if you use Bloomers by itself and want it to have a little volume, you can enable bloomers_untight.

.. admonition:: Target List
	:class: refbox

	:Bloomers: bloomers_untight

|

.. image:: /images/blendshapes/bloomers-untight.gif
	:align: center

|

Skirt1
------
Skirt1 has one corrective morph target.

.. admonition:: Target List
	:class: refbox

	:Skirt1: sit_corrective

|

If you need a pose for the character to sit down, there might be some issues because the skirt is very short and skinned to the thigh bones, it will looks akward and unnatural. 

With Cloth simulation ON:

.. image:: /images/blendshapes/sit1.jpg
	:align: center

|

Morph targets doesn't work together with Cloth so you need to turn Off Cloth Simulation:

.. image:: /images/blendshapes/turn-off-cloth-simulation.jpg
	:align: center

|

.. image:: /images/blendshapes/sit2.jpg
	:align: center

|

Turn on sit_corrective morph target for the skirt.

.. image:: /images/blendshapes/sit-corrective-morph-target.jpg
	:align: center

|

Animations with Morph Targets
=============================

There's only one animation asset that has morph target animation for Meryl. It is inside the :folder:`Animations` \> :folder:`FacialExpressions` folder.

|

.. image:: /images/blendshapes/content-anim-smile-blink.jpg
	:align: center

|

Anim_smile_blink
----------------

There is no skeletal animation data inside :guilabel:`Anim_smile_blink` so the character is not moving, but it has morph target animation of the character smiling and blinking.

The Addictive Setting for this animation asset is set to Local Space.

.. image:: /images/blendshapes/anim-smile-blink-asset-settings.jpg
	:align: center

|

You can use :guilabel:`Anim_smile_blink` inside an Animation Blueprint to add facial expressions to existing animations (blending morph target animation to skeletal animation).

.. image:: /images/blendshapes/anim-smile-blink-anim-blueprint.jpg
	:align: center

|

