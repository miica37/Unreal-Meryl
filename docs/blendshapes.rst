

###############################
Morph Targets (or Blendshapes)
###############################

There are a few mesh that contains morph targets: Head, Eyes, Bloomers and Skirt1

Head
====
Contains about 55 facial morph targets for creating different facial expressions. They are created by following `Apple's ARKit documentation <https://developer.apple.com/documentation/arkit/arfaceanchor/blendshapelocation/>`_, so you should be able to use them with Live Link Face.

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
====
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
========
To prevent Bloomers mesh from intersecting with the skirt, it is modeled to tightly fit the skin but if you use Bloomers by itself and want it to have a little volume, you can enable bloomers_untight.

.. admonition:: Target List
	:class: refbox

	:Bloomers: bloomers_untight

|

.. image:: /images/blendshapes/bloomers-untight.gif
	:align: center

|

Skirt1
======
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

