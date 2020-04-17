---
title: Maps with Leaflet.js
date: "2018-08-19 04:00:00"
url: "/leaflet"
description: "Integration of leaflet.js provides mobile-friendly interactive maps."
author: Lionel VICTOR
image: "img/unsplash-photos-nXt5HtLmlgE.jpg"
credit: "https://unsplash.com/photos/nXt5HtLmlgE"
thumbnail: img/unsplash-photos-nXt5HtLmlgE.tn-500x500.jpg
classes:
- feature-highlightjs
- feature-leaflet
- feature-figcaption-hidden
categories:
- Demo
---
Story integrates [Hugo Leaflet][hugo_leaflet_home]
and allow you to embed maps and GPX trails in your blog posts.

This article demonstrates a handfull of the possibilities offered by this
powerful combination.

<!--more-->

### Pre-requisites
Just like many other Story's capabilities you **MUST** enable the leaflet
[feature](/features) by adding the following class to your article's front
matter:

```yaml
---
classes:
- feature-leaflet
---
```

### Map only

Once the `feature-leaflet` class have been added to your article, embedding
a simple map merely requires using the `leaflet-map` hugo shortcode. And you
don't have to take my word for it ; Just take a look at the following code:

```plaintext
{{</* leaflet-map mapId="first_map" mapHeight="500px" mapWidth="100%" mapLat="43.2500000" mapLon="5.4500000" /*/>}}
```

This is rendered as follows:

{{< leaflet-map mapId="first_map" mapHeight="500px" mapWidth="100%" mapLat="43.2500000" mapLon="5.4500000" zoom="12" scrollWheelZoom="false" />}}

Here follows a list of parameters that can be used with the `leaflet-map`
shortcode _(Except for the `caption` parameters that have been added for 
Story, this list come directly from the [Hugo Leaflet][hugo_leaflet_home] site_).

#### Story's specific parameters:

|  Parameter      | Description                                                                        | Mandatory | Default           | Possible values           |
|:---------------:|:----------------------------------------------------------------------------------:|:---------:|:-----------------:|:-------------------------:|
| caption         | Text to be displayed below the map                                                  | _no_    | ""                 | any string                |

#### Parameters from the original [Hugo Leaflet][hugo_leaflet_home] project

|  Parameter      | Description                                                                        | Mandatory | Default           | Possible values           |
|:---------------:|:----------------------------------------------------------------------------------:|:---------:|:-----------------:|:-------------------------:|
| mapHeight       | Map height size                                                                     | _no_    | "400px"            | any number in px          |
| mapWidth        | Map width size                                                                      | _no_    | "100%"             | any number in px or %     |
| **mapLat**      | Latitude where to center the map                                                    | **yes** | ""                 | any valid coords number   |
| **mapLon**      | Longitude where to center the map                                                   | **yes** | ""                 | any valid coords number   |
| **mapId**       | Unique id. Useful for add multiple map in the post with same longitude and latitude | _no_    | md5(mapLat,mapLon) | any string                |
| zoom            | The zoom level. If set, it must be parsable as int.                                 | _no_    | "13"               | any number                |
| scrollWheelZoom | Enable or disable zoom with mouse scroll wheel                                      | _no_    | "true"             | `"true"` or `"false"`     |


### Map's unique identifier
Maps **MUST** be distinguished by a unique identifier. As you can see in the
above parameters list, a default identifier is computed from the digest of
the coordinates that are provided to the `leaflet-map`.

If you plan on re-using the same map with identical coordinates, then this
computed identifier will be the same for all your maps and this will viloate
the unicity constrain.

In that case, you shall provide unique `mapId` values and make sure that
they are indeed different from each other. You must do that in each and every
map that may be duplicated in your page.

### Direct links to your maps
In most cases, leaving [MapId](#maps-unique-identifier) to its default value
is a good idea. However, because it is based on cryptographic primitives, it
is not always easy to guess what this default value will be.

When you fix the `mapId`, then you can create leverage on this knowledge to
forge [direct links](#mapid_first_map) to your maps as follows:

```plaintext
[a link to my map](#mapid_<your_id_here>)
```

### Map with GPX track

You can share your hikes, motorcycle rides, snowshoeing trails, etc... by
adding a GPX track to your map _(You don't need to provide coordinates,
leaflet will center the track for you but [be careful that your map has
a unique id](#maps-unique-identifier))_:

```plaintext
{{</* leaflet-map mapHeight="400px" mapWidth="100%" ... */>}}
    {{</* leaflet-track trackPath="les_bories_de_tallagard.gpx" downloadIcon=true caption="Discover shepherd shelters in Provence" /*/>}}
{{</* /leaflet-map */>}}
```

As an exemple, the GPX trail from the above snippet comes from a nice
one hour walk in [Provence](https://en.wikipedia.org/wiki/Provence)
_(a region of southeastern France)_. Leaflet will add the elevation
profile as follows:

{{< leaflet-map mapHeight="400px" mapWidth="100%" mapId="les_bories_de_tallagard" >}}
    {{< leaflet-track trackPath="les_bories_de_tallagard.gpx" markerIconShape="star" graphDetached=false graphCollapsed=true graphWidth=300 downloadIcon=true caption="Discover shepherd shelters in Provence" >}}
{{< /leaflet-map >}}

#### Story's specific parameters:

|  Parameter    | Description                                                                            | Mandatory | Default | Possible values |
|:-------------:|:--------------------------------------------------------------------------------------:|:---------:|:------:|:----------------:|
| downloadIcon  | whether we shall display the download icon and provide a download link for the GPX trail | _no_    | false | true of false     |
| caption       | A caption for the track                                                                  | _no_    | ""    | any string        |
| graphTheme    | Elevation graph theme _(in addition to leaflet existing themes)                          | _no_    | "story-theme"   | `"story-theme"` or any theme from the original library |

#### Parameters from the original [Hugo Leaflet][hugo_leaflet_home] project

|  Parameter           | Description                                                 | Mandatory | Default           | Possible values           |
|:--------------------:|:-----------------------------------------------------------:|:---------:|:-----------------:|:-------------------------:|
| **trackPath**        | Your GPX file. You must place in `static/gpx` folder.        | **yes** | ""                         | any filename like `"my_track.gpx"` |
| lineColor            | Line track color                                             | _no_    | "#006EFF"                  | any valid hex color |
| lineWeight           | Line track weight on the map                                 | _no_    | "3"                        | any number |
| lineOpacity          | Line track opacity on the map                                | _no_    | "1"                        | decimal range from 0 to 1 |
| graphPosition        | Elevation graph position on the map. Not valid if you use `graphDetached` | _no_    | "topright"    | `"myLocation"`    |
| graphTheme           | Elevation graph theme already present                        | _no_    | "steelblue-theme"   | `"steelblue-theme"`, `"lime-theme"` or `"purple-theme"` |
| graphWidth           | Elevation graph width. Not valid if you use `graphDetached`  | _no_    | "500"               | any number         |
| graphHeight          | Elevation graph height                                       | _no_    | "150"               | any number |
| graphFollowMarker    | Auto zoom on the mouse movement over the map                 | _no_    | false               | `true` or `false` |
| graphCollapsed       | Hide elevation graph below the button                        | _no_    | false               | `true` or `false` |
| graphDetached        | Detach elevation graph outside map                           | _no_    | true                | `true` or `false` |
| markerIcon           | Waypoint Fontawesome icon name                               | _no_    | "fa-thumb-tack"     | `"fa-thumb-tack"` (see fontawesome documentation) |
| markerIconColor      | Waypoint icon color                                          | _no_    | "cyan"              | `"red"`, `"orange-dark"`, `"orange"`, `"yellow"`, `"blue-dark"`, `"cyan"`, `"purple"`, `"violet"`, `"pink"`, `"green-dark"`, `"green"`, `"green-light"`, `"black"`, `"white"` |
| markerIconShape      | Waypoint icon shape                                          | _no_    | "penta"             | `"circle"`, `square`, `penta` or `star` |
| markerIconClasses    | Extra classes for extends icon css                           | _no_    | "fa-icon-marker"    | `"my-class my-second-class"` |
| markerStartIcon      | Start Waypoint Fontawesome icon name                         | _no_    | "fa-play"           | `"fa-play"` (see fontawesome documentation) |
| markerStartIconColor | Start Waypoint icon color                                    | _no_    | "green-light"       | `"red"`, `"orange-dark"`, `"orange"`, `"yellow"`, `"blue-dark"`, `"cyan"`, `"purple"`, `"violet"`, `"pink"`, `"green-dark"`, `"green"`, `"green-light"`, `"black"`, `"white"` |
| markerStartIconShape | Start Waypoint icon shape                                    | _no_    | "circle"            | `"circle"`, `square`, `penta` or `star` |
| markerStartIconClass | Extra classes for extends start icon css                     | _no_    | "fa-icon-marker fa-icon-start-stop" | `"my-class my-second-class"` |
| markerEndIcon        | End Waypoint Fontawesome icon name                           | _no_    | "fa-flag-checkered" | `"fa-flag-checkered"` (see fontawesome documentation) |
| markerEndIconColor   | End Waypoint icon color                                      | _no_    | "red"               | `"red"`, `"orange-dark"`, `"orange"`, `"yellow"`, `"blue-dark"`, `"cyan"`, `"purple"`, `"violet"`, `"pink"`, `"green-dark"`, `"green"`, `"green-light"`, `"black"`, `"white"` |
| markerEndIconShape   | End Waypoint icon shape                                      | _no_    | "circle"            | `"circle"`, `square`, `penta` or `star` |
| markerEndIconClasses | Extra classes for extends end icon css                       | _no_    | "fa-icon-marker fa-icon-start-stop" | `"my-class my-second-class"` |


### Map with one marker

You can showcase one particular place with a single marker:

```plaintext
{{</* leaflet-map mapHeight="300px" mapWidth="100%" mapLat="44.9178069" mapLon="4.8852736" zoom=18 */>}}
    {{</* leaflet-marker markerLat="44.9175319" markerLon="4.8855297" markerContent="Gastronomic restaurant <em>(3 Michelin Star)</em>" */>}}
{{</* /leaflet-map */>}}
```

{{< leaflet-map mapHeight="300px" mapWidth="100%" mapLat="44.9178069" mapLon="4.8852736" zoom=18 >}}
    {{< leaflet-marker markerLat="44.9175319" markerLon="4.8855297" markerContent="<strong>Maison PIC</strong><br/><em>(3 Michelin Star)</em><br/>Gastronomic restaurant" >}}
{{< /leaflet-map >}}

or many places at once _(by the way notice the use of the "caption" parameter)_:

{{< leaflet-map mapHeight="500px" mapWidth="100%" mapLat="44.93012" mapLon="4.8929719" zoom=14 caption="Starred Michelin guide restaurants in Valence" >}}
    {{< leaflet-marker markerLat="44.9324959" markerLon="4.8865007" markerContent="La Cachette" >}}
    {{< leaflet-marker markerLat="44.9175319" markerLon="4.8855297" markerContent="Maison PIC" >}}
    {{< leaflet-marker markerLat="44.9327024" markerLon="4.8908747" markerContent="Flaveurs" >}}
{{< /leaflet-map >}}

Just like other sub-shortcodes, `leaflet-marker` takes a number of arguments that
we repeat below as they come directly from the [Hugo Leaflet][hugo_leaflet_home] site:

| Parameter     | Description                        | Mandatory | Default | Possible values         |
|:-------------:|:----------------------------------:|:---------:|:-------:|:-----------------------:|
| **markerLat** | Latitude where to place the marker  | **yes** | ""       | any valid coords number |
| **markerLon** | Longitude where to place the marker | **yes** | ""       | any valid coords number |
| markerContent | Popup content text                  | _no_    | ""       | any text, html accepted |

[hugo_leaflet_home]: https://github.com/altrdev/hugo-leaflet/blob/master/README.md "Hugo Leaflet home page..."

Read next: [Story's Embedded Screencasts and Videos](/videojs/).
