scala-geohash aims to provide the basic tools to work with Geohashes in idiomatic Scala.

**Basic Usage**

*Encode a point as GeoHash*

```scala
import org.chobeat.scalageohash.GeoHash

val precision = 12
GeoHash.encodeGeohash(-23.12, -12.33, precision)
```

```scala
import org.chobeat.scalageohash.{GeoHash,GeoPoint}

val precision = 12
val p = GeoPoint(-90.0, -180.00)
GeoHash.encodeGeohash(p, precision)
```

*Decode a GeoHash*


```scala
import org.chobeat.scalageohash.{GeoHash,GeoPoint}
import org.chobeat.scalageohash.GeoHash.BoxRange
import org.chobeat.scalageohash.ImplicitConversions._
val geohash = "5667gf"
val ((latW, latE), (lonN, lonS)): BoxRange = GeoHash(geohash).boxRange
val (lat,lon) = GeoHash(geohash).centroid
```

*Get the neighbour of a GeoHash*


```scala
import org.chobeat.scalageohash.{GeoHash,GeoPoint}
import org.chobeat.scalageohash.Directions._
import org.chobeat.scalageohash.ImplicitConversions._
val geohash = GeoHash("gbsuv")
val neighbour = geohash.getNeighbour(North)
```

*Get all the neighbours of a GeoHash*


```scala
import org.chobeat.scalageohash.{GeoHash,GeoPoint}

val geohash = GeoHash("gbsuv")
val neighbourSet = geohash.getNeighbourSet()
```

