
###############################
Updates Log
###############################

.. role:: folder
.. role:: material
.. role:: material2

.. _updates_v2:

2.0 (11/07/2022)
--------------------

Meshes:
   *  New Outfit
     -  < SK_Meryl2 >
     -  < SK_Meryl_Hair2 >
     -  < SK_Meryl_Hair3 >
     -  < SK_Meryl_Hair4 >
     -  < SK_Meryl_Hat2 >
     -  < SK_Meryl_Top2 >
     -  < SK_Meryl_Skirt2 >
     -  < SK_Meryl_Shoe1 >
     -  < SK_Meryl_Bloomers > (replacing previous `Underwear`)

   *  Added a few Static Meshes
     -  < SM_Meryl_Flowers >
     -  < SM_Meryl_Hat1 >
     -  < SM_Meryl_Hat2 >

   *  Renamed textures and materials
     -  < Head >     ⟶ < Head1 >
     -  < Body >     ⟶ < Body1 >
     -  < Hat >      ⟶ < Hat1 >
     -  < Hairs >    ⟶ < Hair1 >
     -  < Tops >     ⟶ < Top1 >
     -  < Bottoms >  ⟶ < Skirt1 >
     -  < Leggings > ⟶ < Leggings1 >
     -  < Boots >    ⟶ < Boots1 >
  
   *  Added :ref:`LOD1 <lods>`  (nearly half the previous polycount)
   *  Added Proxy Cloth Simulation to Hair1, Hair2 and Hair3 and Hair 4
   *  Fixed Body's elbow area not being symmetrical.
   *  Fixed Eye close blendshapes intersection with Eyelids
   *  Fixed Head blendshape MouthRollUpper and MouthRollLower (previously swapped)
 
Materials:
   *  Added [ M_Meryl_Clothes_Master ] to improve :ref:`Performance <performance>` (:ref:`more info <clothes_master>`)
   *  Added :ref:`Duo Eye material <duo_eyes>` ( [ M_Duo_Eyes_Master ] and [ MI_Meryl_Duo_Eyes_01 ] )
   *  Added 5 Skin Presets for the new outfit
   *  Added 6 new eyes color Presets
   *  Added [ M_Generic_Vert_Offset_Master ] and [ M_Generic_Tint_Vert_Offset_Master ] to offset the skirt mesh
 
Preview Map:
   *  Added Grid Material ( [ M_Grid ] and [ MI_Grid_Floor ] ) for the Preview level
   *  Added Wireframe material ([ M_Wireframe ] and [ MI_Wireframe ])  for demo purposes in the Preview level

Animations:
   *  Added < Anim_Echo_Walk_Fwd >
   *  Added < Anim_Echo_Idle_Long >
   *  Modified < Anim_Yin_Idle_Combat > slightly

Dynamics:
   *  Added < SK_Meryl_Hair4_Dynamic >, it has extra hair bones for Hair4 for dynamic simulation
   *  Renamed < SK_Meryl_EXB_Bottoms > to < SK_Meryl_Skirt1_Dynamic >

Textures:
   * Added *Master* Textures to be used just for the Master Materials (in the folder :folder:`Meryl\\Textures\\Master` : < T_Master_D >, < T_Master_MRAO >, < T_Master_N >, < T_Master_RGB >)
   *  Fixed Body normal map textures (seams on Neck area)

Fbx:
   * Added Fbx files (in the folder :folder:`Meryl\\Fbx`)

Unreal Engine 5:
   * Added IK Rig for retargeting in UE5 (in the folder :folder:`Meryl\\Meshes` < IK_Meryl > )

Documentation:
   * More efforts on documentation and updated to reflect new changes

|

1.05 (08/06/2022)
--------------------

 * Fix incorrect orientation of root bone

|

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

|
