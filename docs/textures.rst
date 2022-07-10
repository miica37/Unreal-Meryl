
###############################
Textures
###############################

.. role:: material2

.. image:: /images/textures/content-textures.jpg
    :align: center

Textures for Meryl are created in Substance Painter and Photoshop.

.. _textures:

PBR Textures
------------
Meryl's textures are created using PBR (Physically Based Rendering) **Metallic Roughness** Workflow. 

A mesh part usually comes with 4 basic textures: Diffuse ( [ T_***_D ] ), Normal ( [ T_***_N ] ), MRAO  ( [ T_***_MRAO ] ) and RGB  ( [ T_***_RGB ] ).

.. image:: /images/textures/content-texture-set.jpg
    :align: center

MRAO
----
MRAO stands for Metallic, Roughness and AO (Ambient Occlusion).

Instead of having 3 different textures (Metallic, Roughness and AO), this texture packs them into Red, Green and Blue Channel of a single texture.

RGB
---
RGB stands for Red, Green, Blue.

This texture contains 3 masks, each packed into the Red, Green and Blue channel. The different masks are used to tint different areas of the color texture.

Hairs RGB
^^^^^^^^^
.. image:: /images/textures/content-hairs-rgb-highlight.jpg
    :align: center

|

.. image:: /images/textures/hair4-rgb-textures.jpg
    :align: center

Hairs come with 2 (or 3) RGB masks, giving the hair a number of different looks.

T_Uniform_RGB
^^^^^^^^^^^^^
[ T_Uniform_RGB ] can be used in place of a certain mesh that doesn't come with a RGB texture.

It can also be used if you want to change the color of the **whole** mesh.

|
