# Static Map Service ArcGIS
You will be able to get static maps like this:

```
<img src="http://<service_url>/?center=Brooklyn+Bridge,New+York,NY&zoom=13&size=600x300&maptype=streets&markers=color:purple%7C40.702147,-74.015794&markers=color:orange%7C40.711614,-74.012318&markers=color:orange%7C40.718217,-73.998284">
```

To install this service you just need to run:
```zsh
$ git clone git@github.com:esri-es/Static-Map-Service-ArcGIS.git
$ npm install
$ node index.js
```
Allowed parameters: 

Param| Type | Default value | Summary
--- | --- | --- | ---
basemap|string|topo|Allowed: satellite, topo, light-gray, dark-gray, streets, hybrid, oceans, national-geographic, osm
maptype|string|topo|basemap alias
zoom|int|5|Allowed: from 1 to 15
latitude|double|40.432781|Allowed: -90 <= x >= 90 (map center) **(pending)**
longitude|double|-3.626666|Allowed: 180 <r= x >= 180 (map center) **(pending)**
address|string|None|This uses the single address API (no credits consuming) (map center)
markers|array of markers objects|None|Bellow you will find another table with the description
size|string|300x300|<Width>x<Height>
format|string|PNG32|Allowed: PNG32, PNG8, JPG, GIF, SVG, SVG2

To center the map you must use: *address* **OR** *latitude and longitude*, never both.

Markers properties:

Param| Type | Default value | Summary
--- | --- | --- | ---
latitude|double|None|Allowed: -90 <= x >= 90
longitude|double|None|Allowed: 180 <r= x >= 180
color|string|None|Available at this time: orange|purple
xoffset|int|0|X Offset of the marker
yoffset|int|0|Y Offset of the marker

# Testing environment
You can test it using the [testing instance at Heroku](https://staticmapservice.herokuapp.com/?center=Brooklyn+Bridge,New+York,NY&zoom=13&size=600x300&maptype=streets&markers=color:purple%7C40.702147,-74.015794&markers=color:orange%7C40.711614,-74.012318&markers=color:orange%7C40.718217,-73.998284)
