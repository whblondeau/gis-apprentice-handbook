# WTF is...

## WTF is a Cartographic Projection?
This is an important question, since GIS software without a defined Cartographic Projection is like a door without hinges: it just won't work, at all.

[Cartographic Projections](http://en.wikipedia.org/wiki/Map_projection) are, to be basic and strict about it, mathematical procedures that transfer a point on the Earth's surface to a point on a flat surface (such as a paper map or a computer screen.) They are also guaranteed to work in reverse, starting with a point on a map and transferring that location back to the Earth's surface. In other words, a Cartographic Projection is the round-trip geometry that makes your map useful. When you click on a Google Map, you know that the click is indicating the point on Earth's surface that it looks like it's indicating. 

_The visual picture has the property of representing location accurately._ But... Why, why, _why_ do we need to go through a lot of **math** to make this happen?

### Why the math
Well, basically, because the Earth is spherical. (Yes, you persnickety geodetic bitches, I know: it's _technically_ an oblate ellipsoid, and even more technically a geoid; but at the WTF level of abstraction it's just a fucking sphere, all right? The more technical and arcane geometric considerations matter to the people who worry about getting their GPS fix accurate to within a few meters. We're considering an entire planet.) The Earth, then, is a sphere; but maps are always flat surfaces for practical reasons.

The mathematical difference between a spherical surface and a flat surface is profound. This is because spheres are an example of a _compound curved_ surface, on which you cannot ever lay a straight line. As a result, 
t's impossible to transfer shapes from a curved surface to a flat surface without distorting those shapes. **Example:** you have a sizable piece of orange peel, and you want to flatten it on the table, with its outside up. As you apply the mighty force of your brawny arm to this worthy task, you will see the pores in the center of the peel being mashed closer together, and possibly the ones around the edges being stretched out. By the same token, a flat surface won't wrap around a sphere without folding or distorting. The example of this is to take another orange, not peeled, and try to wrap a piece of paper around it _smoothly_, without any crinkling or folding. Go ahead, I double dog dare you. We'll wait.

OK, hopefully you are convinced about the geometrical incompatibility of flat surfaces and spherical surfaces. But there's another kind of surface in 3D space that we need to consider. Its right mathematical name is _developable_, but I prefer to call it "flattenable". A flattenable surface is one that is not flat, but on which you _can_ lay a straight line. This is a _simply curved_ surface, and the easiest way to identify it is that you can create it from a flat piece of paper by curling or folding it. You can always unroll the curl, or unfold the creases, and get back to a purely flat piece of paper. _You can't do that with the orange peel_, because the orange peel cannot be flattened without distortion.

The most cartographically significant flattenable surfaces are the _cylinder_ and the _cone_. (Specifically, the right circular cylinder and cone.)

### An exercise in case you don't get it

 1. Take a largish sheet of paper.

 2. Roll it into a tall slender cone about 7 inches in diameter at the base. Don't worry about the unevenness of the bottom rim.

 3. Put it on your head like a hat, take a fucking selfie, and post that online.

 4. Unroll the cone and flatten it out.

 5. Repeat steps 2-4 until you really grasp the flattenable nature of the cone. Don't lose faith: _It will come to you_, I swear.

### How does a projection get built?

A Cartographic Projection is simply a way of solving the problem of representing the spherical Earth on a flat surface - and solving it in a useful way. There is an infinite number of possible projections, but only a few of them serve a useful purpose.

The most useful ways that have so far been introduced are, as mentioned, linear projections on a plane, a cylinder, or a cone. Like this:
<img src='https://github.com/whblondeau/gis-apprentice-handbook/blob/master/images/rice_projections.jpg' alt='drawings of planar, cylindrical, and conic projections'/>

There is one truth about any projection of the Earth onto a flat, or flattenable, surface: **They distort. All of them.** For the same reason as the flattened orange peel gets squeezed and stretched. You just have to choose what kind of distortion you want.

There is one very important principle: _the more local the map is, the less the distortion will happen._ In projections that have practical value, anyway. But a smallish town map can be done by a surveyor without caring at all about the curvature of the earth.


## WTF is a Mercator projection?
There are two answers to this.

A Traditional Mercator map is a cylindrical projection. The cylinder's axis is the same as the Earth's axis, and the cylinder is tangent to the Equator. This is the great traditional map for navigation, especially at sea. The reason? On a traditional Mercator projection the parallels of latitude are precisely horizontal; the meridians of longitude are precisely vertical; and the spacing of the lines is such that _direction is the same as it is on the Earth._ To explain the significance of this, suppose you are out on the rolling sea, acting as navigator on a ship. One of your main responsibilities is to give the helmsman a course to steer so you will head towards where you want to be. Let's say, and why not, that you're heading for Bristol in England. Obviously there's a direction that points the ship towards Bristol, right?

OK, trick question. Because of the way we reckon direction and position, there are a couple of options that fit that general idea. We can actually point the bow towards Bristol; or we can just say to the helmsman, "Steer course 051". However, these do not result in the same track. If your first thought is "Huh?" that's pretty standard. Our landbound sense of direction doesn't make distinctions between maintaining a compass heading, on the one hand, and walking straight towards our destination, on the other. There are reasons for this: mainly that on land we are constrained by topography, and so we follow roads and paths, avoid ridges and swamps, and so on; but also because we don't generally use charting and navigation to get around.

The ocean, however, is 1) very fucking big and 2) comparatively empty of obstacles. There are not paved roads, bridges, etc. Water is water, as long as it's deep enough. If anything's in your way, it's probably another ship; and there are rules covering who has to alter course or speed, and how much, when vessels come close enough to each other to be worrisome. So, at sea, you really want to do that straight-line-to-my-destination thing. Save fuel, save time, make it to the fleshpots of Bristol all the sooner. The basic problem, however, lies in what can be called a "straight line". There are two of those. I will call them the "helmsman's" straight line, and the "rubber band" straight line.

#### Helmsman's Straight line: a _rhumb line_ (for mathematicians, a _loxodrome_)

The helmsman's notion of "straight" is something like, "I keep the ship on the same heading." And, subject to the actions of wind, wave, current, and a sleepy/stoned/otherwise inattentive helmsman, doing this will take the vessel along a rhumb line. Except for a few special headings such as East, West, North, and South, a rhumb line is actually something that, plotted on a globe, you would immediately identify as a spiral. (Unless you're a mathematician, in which case you'd say, "Bitch please: a loxodrome as ever was, that is.") The helmsman's "straight line" is straight in the sense that it's constant in its reference to north. However, since you're traversing a fair chunk of the globe's surface, you are actually winding yourself round and round, closer and closer to one of the poles, like a dog winding its leash around a tree.
<img src='http://en.wikipedia.org/wiki/File:Loxodrome.png#file' alt='loxodrome image on globe, from wikipedia'/>

#### Rubber band's straight line: a _Great Circle_

The other kind of straight line is more meaningfully straight from a global perspective. I'm calling it the rubber band line because it's what you get when you stretch a rubber band between any two points on the globe.


## WTF is a shapefile?
Oh gosh. Why couldn't you have asked something easy, like "What are the philological implications of differences in usage of the subjunctive between the respective works of Christopher Marlowe and William Shakespeare?" Or, "What are Maxwell's Equations and what do they mean?" Or even, "Why didn't the chart-topping success of ['Come On Eileen'](http://www.youtube.com/watch?v=jC1vtG3oyqg) in 1982 spawn a vast imitative wave of Celtic Motown?" (OK, the last one isn't a fair example: it's one of those mysteries that has no real answer.)

The shapefile is a vector geospatial data format defined by ESRI in order to foster data interchange between ESRI and non-ESRI systems. That's a very good idea. The implementation is, however, unfortunate. Perhaps the best excuse for it is that this was defined long before XML appeared; concepts of data interchange were pretty infantile back in 1992.

The key thing to remember about a shapefile is that it's a cluster. 

In other words, it's not a single file. It is a group of separate files in corresponding sequence: if you pick the 35th record out of each file in a shapefile, all of those records combine to provide all of the content of the shapefile's 35th record.

The shapefile contains 3 mandatory files: a geospatial coordinate "shape" file; an index on that shape file; and a set of non-spatial "attributes" that are applied to the corresponding coordinate in the first file.


