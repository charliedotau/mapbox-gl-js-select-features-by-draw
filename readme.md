## Intro

This example is a variant on the [Highlight Features within a bounding box example](https://www.mapbox.com/mapbox-gl-js/example/using-box-queryrenderedfeatures/) on the `Mapbox` website.

Their example demonstrates highlighting features (in this case US Counties), by "drawing" a bounding box.   

## selecting features by a bounding box? pffffttt.
Using a rectangle to select map features provides a very limited user experience. The things a user wants to select rarely fit neatly into a rectangle! 


## Goodbye bounding box, hello polygon

A better user experience for feature selection, would be to allow the user to draw a polygon.  This repo is a demo of this in action.

## Motivation

I articulate [here](https://github.com/mapbox/mapbox-gl-js/issues/4787) - why this user experience might be useful.  

## Basic logic

Whilst the logic that underpins this demo is fairly simple - you will see  from [this Mapbox GL JS github ticket](https://github.com/mapbox/mapbox-gl-js/issues/4787) that the thinking is not mine!

1. use `Mapbox GL Draw` to enable a user to draw a polygon
2. use `Turf js` to get the bounding box of the user's polygon
3. use `queryRenderedFeatures` method to query the features within the bounding box
4. use `Turf js` to identify the subset of queryFeatures that intersect with the polygon drawn by the user.

