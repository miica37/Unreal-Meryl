
###############################
Performance Tests
###############################

.. _performance:

I created a map to measure the performance of Meryl on 3 main aspects: 

 * the reduction of Polygons (LODs)
 * the reduction of Material Slots
 * the use of Clothing

There are 256 instances of Meryl in the scene and \`stat unit\` is used to show the performance.

| \* Meryl 1b reduces a few material slots (from 13 to 8).
| \* Meryl 1c reduces even more material slots (from 8 to 4),
|   it is also not able to do any clothing simulations due to the removal of clothing material slots.

|

.. image:: /images/performance/performance-test-map-thumbnail.jpg
	:align: center

|

.. image:: /images/performance/performance-test-map-viewport.jpg
	:align: center

|

Results
-------

.. image:: /images/performance/performance-test-results.jpg
	:align: center

|

Use of Clothing
===============

The use of Clothing seems to have the biggest impact on performance. Disable clothing reduces calculation time by nearly 50%. It reduces the calculation time even more if you reduce the materials at the same time.

.. image:: /images/performance/performance-test-results-highlight-clothing.jpg
	:align: center

|

Reduction of Material Slots
===========================

The reduction of material slots also have positif results, it reduces calculation time by ~20%.

.. image:: /images/performance/performance-test-results-highlight-materials-reduction.jpg
	:align: center

|

Reduction of Polygons
=====================

The amount of polygons doesn't seem to have much impact on the performance. Reducing the polygons by half seems to only reduce the calculation time by less than 5%.

Interestingly though it seem to works better with clothes turned off together with the reduction of materials.

.. image:: /images/performance/performance-test-results-highlight-lods.jpg
	:align: center

|

Conclusions
===========

Consider working on Meryl with a more simple material while iterating on the looks. There will be less shader compilation time if you are going to make changes to the material settings often.

Update material to master clothes material after you have nailed the look. You will need to do Mesh Merge as well.

Disable cloth simulations and Use Master Clothes Material **together** where you need max performance.

.. warning::
	Disable cloth simulations will cause skirt mesh intersecting with legs

|
