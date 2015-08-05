# Static Map Service ArcGIS
You will be able to get static maps like this:

```
<img src="http://<service_url>/?center=Taracon,Spain&zoom=7&size=600x300&maptype=streets&markers=color:purple|40,-3&markers=color:orange|40,-3|xoffset:30|yoffset:30">
```

To install this service you just need to run:
```zsh
$ git clone git@github.com:esri-es/Static-Map-Service-ArcGIS.git
$ npm install
$ node index.js
```
Allowed parameters (concatenate using &): 

Param| Type | Default value | Summary
--- | --- | --- | ---
basemap|string|topo|Allowed: satellite, topo (terrain is an alias), light-gray, dark-gray, streets (roadmap is an alias), hybrid, oceans, national-geographic, osm
maptype|string|topo|basemap alias
zoom|int|5|Allowed: from 1 to 15
center|address or lat,lon|None|Map center
markers|array of markers objects|None|Bellow you will find another table with the description
size|string|300x300|<Width>x<Height>
format|string|PNG32|Allowed: PNG32, PNG8, JPG, GIF, SVG, SVG2

Example using an address: 
```
?center=Taracon,Spain&zoom=7&size=600x300&maptype=streets&markers=color:purple|40,-3
```
Or using a latitude and longitude
```
?center=40,-3&zoom=7&size=600x300&maptype=streets&markers=color:purple|40,-3
```

Markers properties (concatenate using |):

Param| Type | Default value | Summary
--- | --- | --- | ---
latitude|double|None|Allowed: -90 <= x >= 90
longitude|double|None|Allowed: 180 <r= x >= 180
color|string|None|Available at this time: orange|purple
xoffset|int|0|X Offset of the marker
yoffset|int|0|Y Offset of the marker

Example: 
```
&markers=color:purple|40,-3&markers=color:orange|40,-3|xoffset:30|yoffset:30
```

# Testing environment
You can test it using the [testing instance at Heroku](https://staticmapservice.herokuapp.com/?center=Brooklyn+Bridge,New+York,NY&zoom=13&size=600x300&maptype=streets&markers=color:purple%7C40.702147,-74.015794&markers=color:orange%7C40.711614,-74.012318&markers=color:orange%7C40.718217,-73.998284)
