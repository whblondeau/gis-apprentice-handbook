# OpenLayers: the primary Open Source GIS client for web apps

### Resources and References

[openlayers.org](http://openlayers.org/) The OpenLayers project website

[The book of OpenLayers 3](https://leanpub.com/thebookofopenlayers3), Antonio Santiago: I have this book. This guy knows his stuff.

[OpenLayers 2.10 Beginner's Guide](http://www.amazon.com/gp/product/B005685FB0), Erik Hazzard: I have this book. It's a bit uneven; I get the sense that the author is more skilled with GIS concepts than with code. Which is all right with me: when it comes to code I'm probably not all that educable. GIS/OpenLayer concepts and basics were what I was looking for, and I got a fair amount here.

## The OpenLayers Logical Model

OpenLayers is a client that knows how to communicate with various kinds of GIS services from various providers, and use the map information they return. In order to do that they have created a pretty smart, simple, and reasonable clientside GIS model. 
- All communications with GIS services have the end result of updating the content of the model.

- All user interaction with the OpenLayers model is either viewing the content, or issuing a request for a change. Maybe the change will require new information from a service (change in content), or maybe it won't (change in presentation of existing content).

The OpenLayers model lives in a web page in a browser.

The OpenLayers model defines three kinds of component:

- The **Map**, of which there is only one;
- **Layers**, of which there are usually several;
- **Controls**, of which there are usually several.

### The Map Component

The OpenLayers Map is the fundamental component. It is the thing that actually lives in the web page (in fact, it lives in an HTML &lt;div>

**The primary purpose of the Map is to establish a geospatial coordinate system that resides in the DOM.**

The secondary purposes of the Map are:

- To implement all the math, and the things that come from math. Panning, zoonimg, rotating, etc. The map will send AJAX calls to the server for tiles as needed.

- To recognize user actions: mainly mouse events. The map knows the viewport pixel locations of these events, and translates them to a location in its GIS coordinate system. 

- To make user/DOM _Events_ available, so that registered event handlers will be notified that events of their type have occurred. Mouse clicks and Control interactions are user Events.

- To maintain a collection of Layers. It is the Map's responisbility to:

  - _locate_ those Layers (i.e., move them to the correct x,y coordinates and zoom them as necessary) so that their appearance matches the coordinate system of the Map;

  - _update_ those Layers to ensure they have correct tiles from the servers, based on UI events;

  - manage Layer _order_ so that the browser can present the correct appearance of overlay.

- To maintain a collection of Controls. Just as with Layers, Controls have order and x,y position.

And the cool thing is? You don't have to do _any_ of this manually. The Map takes care of it for you. This is the core functionality of OpenLayers, and oh goodness did they get it right. As mentioned elsewhere, they got it right in the sense of 'not buggy' as well as in the sense of 'I got this'. Here we see OpenLayers at its most awesome.




