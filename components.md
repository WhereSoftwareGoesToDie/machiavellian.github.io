---
title: Components
layout: page
sidebar_link: true
---

Machiavelli implements various components as interchangeable entities - any selection should be compatible with any other selection. 

### backend - _n._ a thing that contains metric data

A backend implementation does not necessarily have to define information about the metric itself, as long as the class library has this information defined, either statically or dynamically. 

### metric - _n_ a data source

One backend may consist of one or more metrics. Metrics can be called in any format, as long as they return a x,y hash of data after class method manipulation. 

### graph - _n._ a visualization format

Given the standardization of metric data, a graph can assume this format, and visualize the data as it sees fit. 

Most of the complexity in the graphing components comes in the ruby views and JavaScript assets. However, server-side logic can still be implemented if required.


Here's some we prepared earlier 
-------------------

Machiavelli natively supports the following components: 

**Backend sources, and metrics**

 * [Vaultaire](https://github.com/anchor/vaultaire), versions 1 and 2
 * [Graphite](https://github.com/graphite-project/graphite-web), v0.9.9 
 * simple JSON feeds, see ((Demonstration Backend))
 * comma-delimited flatfiles, in the form `epoch,value`

**Graphs**

 * [Cubism](https://github.com/square/cubism) graphs, for horizon graphs 
 * [Rickshaw](https://github.com/shutterstock/rickshaw), for standard and stacked views


But wait, there's more!
-------------------------

Backends and graphs can be extended by following the [[Extending Components]] documentation.
