
###############################
Blueprints
###############################

.. role:: folder

Overview
========

.. image:: /images/blueprints/content-blueprints.jpg
    :align: center

The :folder:`Meryl\\Blueprints` folder contains character blueprints and animation blueprints made in Unreal Engine 4.22. These blueprints are based on the third person character template (UE 4.22).

< BP_Meryl > and < BP_Mery2 > use precombined mesh while < BP_Meryl_Modular > shows a modular version of Meryl assembling different mesh parts by using a number of Skeletal Mesh Components to create a different look from the precombined mesh.

< BP_Meryl_Modular_Hair4_Dynamics > and < BP_Meryl_Modular_Skirt1_Dynamics > are examples of blueprints that use :ref:`some different skeletons with extra skirt bones or hair bones <dynamics>` to simulate dynamics.

Some controls added to the < BP_Meryl > and < BP_Mery2 >:
   
   *  Zoom with Mouse Wheel

   *  Pan Camera Vertically with :kbd:`Q` and :kbd:`E`

   *  Press :kbd:`1` to switch between LOD0 and LOD1

|

New Axis Mapping added to Project Settings to work with the blueprints:

.. image:: /images/blueprints/engine-input-settings.jpg
    :align: center
