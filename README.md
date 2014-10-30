The GIS Apprentice's Handbook
=======================

A general GIS resource for apprentice Web programmers. Edited and primarily written by Bill Blondeau.

### Disclaimers

#### No IP warfare here
This repo is being released under the Creative Commons Share-Alike License 2.0.

#### Not a day job project
Please note that, although as this work begins I am working for the US Geological Survey's Center for Integrated Data Analysis, this Handbook has no connection to the USGS. I am not writing in any official work-related capacity. This is a personal undertaking, written on my own time.

This will presumably come as a relief to the USGS. This Handbook is likely to be opinionated to an unprofessional degree, contentious, and (in an attempt to make technical prose more salient through memorable, even vivid devices of analogy and prose) subject to lapses of tone and decorum. 

Nothing herein constitutes any kind of endorsement by the USGS, and nothing herein can be blamed on the USGS. Unless you want to blame them for exposing me to GIS in the first place.

#### Contributors
Personal opinions shared in pull requests will be flagged as the monstrous brainchildren of their authors; unless the opinion is one I share, in which case it will be flagged as inarguably true and admirably perceptive.

No matter how much I love someone's contributions I will not pay for them. I will, however, scrupulously manually credit concepts, ideas, and inspirations not sufficiently documented by GitHub's version control processes.

#### Consistency
Haha. No small foolish hobgoblins here. The content of this Handbook will change a lot, sometimes reversing bold statements, sometimes completely replacing or revising large chunks of content.

<hr/>

## Because somebody had to, sooner or later
GIS is, according to [Wikipedia](http://en.wikipedia.org/wiki/Geographic_information_system), "a computer system designed to capture, store, manipulate, analyze, manage, and present all types of spatial or geographical data."

This repository is much less generic than that. Its purpose is narrower and shallower: to provide a first stop for any GIS programmer looking for information about how to get things done.

Why do we need this?


Well, perhaps _you_ don't, which is fine. In fact, it's kind of a compliment that you're reading this if you don't have to. But I did need a handbook like this, and I do, and I have a hard time believing that nobody else could benefit from it. For whatever reason, fundamental explanations, clear tutorials, reference works, and useful examples are pretty thin on the ground in GIS programming. I've gotten used to resorting to Google searches (yet another dependency on yet another aspiring Evil Empire, I know, I know) whenever I want to find out, quickly, how to use some new software language/library/framework/tool/technique.

I said "for whatever reason", but I actually have some guesses. Maybe people can give some thumbs up/down observations here.
- Although GIS is a hot new field, showing some of the most explosive growth in the industry outside of stupid social mobile apps that let you put a lipstick color picker on your selfies or something, the number of actual working developers may still be small compared to the number of people working on lipstick color pickers etc.

- The bulk of GIS work may still be bound up in the [ESRI](http://www.esri.com/) ecosystem. ESRI, being proprietary, closed-source, and Windows-only, is a nonstarter for my current work. It may be that the open GIS resources, which is what I'm referring to when I talk about the difficulty of finding adequate material online, are used by only a small slice of a much larger GIS community.

- GIS developers may be too busy (or, equivalently, nobody is going to pay them) to provide this kind of general community contribution in sufficient volume.

- Non-ESRI GIS development is still such a young field that there's been little time to accumulate the searchable body of helpful content for which I yearn.

- Really, it's out there after all, and I'm too damn dumb to find it.

I'm sure other factors are in play. However, I'm less concerned with the etiology of this sorry-ass situation than I am with getting around it. My natural instinct is to document whatever I am having a hard time learning. I hope this is useful to others, but there's no question that it will be useful to me.

## What's this Handbook going to cover?

A Handbook, traditionally, is a subject-specific concentration of pertinent definitions, sufficient explanations, and material that would otherwise have to be looked up or chased down. That's pretty much what I'm going for here. The specific subject is GIS software development - primarily on the open source side.

The particular topics here include (I say "include" because I'll miss a lot; and besides, the field won't be holding still):

- **Common definitions and concepts (WTFs):** These are things that span enough of the field that defining them separately makes sense. Some of them are foundational (definitions from Geodesy, for example); some of them are ubiquitous for historical reasons (e.g. ESRI Shapefiles); some of them will inevitably be shit that I made up because it just seemed like a good idea. Explanatory connective tissue, you might call it. The convention here is that these definitions are formulated as "WTF"s, e.g. "WTF is a shapefile?". In some cases the WTF entries will provide links to external or internal discussions in greater detail.

- **OpenLayers:** Most clientside GIS work is done in a browser, which regrettably means javascript. [OpenLayers](http://openlayers.org/) is a big, powerful framework implemented in javascript. Awesomely, it seems pretty bug-free. However, the API documentation is sort of feeble. (People say it's great, but they are likely having a bit of a problem with crystal meth; or else their expectations have been brutalized by the conventions of the javascript community.) Moreover, the new OpenLayers version, 3.0, seems at time of writing to be almost completely undocumented. This portion of the Handbook will attempt to remediate this, both for the 2.13 version and the 3.0.

- **Leaflet:** A more lightweight Javascript GIS client framework. Simpler and less powerful than OpenLayers, but a good choice for a wide range of simpler problem spaces. Leaflet is also open source.

- **GIS Servers:** Descriptions of the different kinds of GIS servers: their nature, their APIs, their governing bodies. These will include proprietary mapping services such as Google and ESRI, but will focus mainly on the [Open Geospatial Consortium](http://www.opengeospatial.org/) service definitions and their [GeoServer](http://geoserver.org/) reference implementation.

- **Python geospatial libraries:** As with so many practical undertakings, Python is excellently represented in the GIS domain. The Handbook will contain as much description and guidance for Python GIS work as I (and any collaborators) can wedge in.

## "Apprentice"? What's that all about?

Apprenticeship, as a concept, appears here in two senses.

First, there's the obvious sense: an apprrentice is a beginner, someone who needs introduction. Orientation. The basics. Covering those basics is the core project of this Handbook.

Second, I plan to approach apprenticeship in the sense it's used in the excellent book [Apprenticeship Patterns](http://shop.oreilly.com/product/9780596518387.do) by Dave Hoover and Adewale Oshineye. (Which I need to reread soon, now that I think of it.) The TL;DR is neatly expressed in the second paragraph of their first chapter, which says, 
<blockquote>The concept of apprenticeship is based on the medieval craft model, where small teams of practitioners work together and inexperienced apprentices help the journeymen and master craftsmen do their work. One of our goals for this book is to inspire the people who love to create software to stay focused on their craft.</blockquote>

These guys are pushing an approach to software development that helps you keep your flame alive, and helps you not let your software development career turn into a boat anchor around your neck. That's a pretty important goal. This Handbook will try to respect and further it.

## Table of Contents



