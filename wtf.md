# WTF is...

## WTF is a shapefile?
Oh gosh. Why couldn't you have asked something easy, like "What are the philological implications of differences in usage of the subjunctive between the respective works of Christopher Marlowe and William Shakespeare?" Or, "What are Maxwell's Equations and what do they mean?" Or even, "Why didn't the chart-topping success of ['Come On Eileen'](http://www.youtube.com/watch?v=jC1vtG3oyqg) in 1982 spawn a vast imitative wave of Celtic Motown?" (OK, the last one is a mystery with no real answer.)

The shapefile is a vector geospatial data format defined by ESRI in order to foster data interchange between ESRI and non-ESRI systems. That's a very good idea. The implementation is, however, unfortunate. Perhaps the best excuse for it is that this was defined long before XML appeared; concepts of data interchange were pretty infantile back in 1992.

The key thing to remember about a shapefile is that it's a cluster. 

In other words, it's not a single file. It is a group of separate files in corresponding sequence: if you pick the 35th record out of each file in a shapefile, all of those records combine to provide all of the content of the shapefile's 35th record.

The shapefile contains 3 mandatory files: a geospatial coordinate "shape" file; an index on that shape file; and a set of non-spatial "attributes" that are applied to the corresponding coordinate in the first file.
