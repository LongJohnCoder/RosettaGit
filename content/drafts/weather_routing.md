+++
title = "Weather Routing"
description = ""
date = 2016-12-18T06:23:52Z
aliases = []
[extra]
id = 19334
[taxonomies]
categories = []
tags = []
+++

{{Draft task|Routing algorithms}}
The weather routing problem has the following parts:
<ul>
  <li> a predicted surface wind direction and speed, at increments of longitude, latitude, and time</li>
  <li> an expected surface current direction and speed, at increments of longitude, latitude, and time</li>
  <li> 'polar data' describing maximum speed of a sailboat at points of sail for a given speed of wind over water</li>
  <li> regions for sailing (the open ocean) and not (the land, shallows, restricted areas, etc.)</li>
  <li> a starting location and time, and a destination</li>
</ul>

Given the above information and a specific path, progress and arrival time are determined. The weather routing problem, conversely, is to determine the path which results in the earliest arrival time.
