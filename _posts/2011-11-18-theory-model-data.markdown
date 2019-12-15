---
layout: post
title:  "Theory, Model, Data"
date:   2011-11-18 14:46:55 -0800
categories: research 
---

A successful research project requires 3 components: Theory, Model and
Data. The definitions of these words from conversations with others
are these.

**Theory** is the concept or idea that leveraged or to be tested (demonstrated).

**Model** is the system or a series of processes such as an algorithm that
implements or tests (demonstrates) the theory.

**Data** is the test results demonstrating the efficacy of using the model,
thereby also confirming the theory.

In the paper on Shape-Carving by Kutulakos, the theory is the principle of
having each ray of light from the surface of the object agree in color, and by
starting with a volume larger than the actual volume of the object and carving
away voxel by voxel, the outcome is necessarily an overestimate of the actual
object volume. The model is the algorithm that implements the shape-carving
algorithm. The data are the volumetric reconstructions resulting from this
method as well as any special parameter value used in the tests. Since the data
shows that the method  can compute the volumetric reconstructions successfully,
the data also confirms the theory that reconstructions can be obtained by
carving away at a volume larger than the actual object by keeping only voxels
that agree in color among its many camera projections.

Data doesn’t come cheaply. 

