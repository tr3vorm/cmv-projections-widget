This widget has been written specifically for [David Spriggs CMV project](https://github.com/DavidSpriggs/ConfigurableViewerJSAPI) to provide a tool for projecting coordinates between specified projections and also for entering coordinates to go to a specific location. 

It allows a user to place a marker on the map, reporting the coordinates at that location in configured coordinate systems. The use can edit the coordinates for any projection within the grid, and the marker will move to the new location as well as updating all projected coordinated.

![screendump](https://github.com/tr3vorm/tr3vorm.github.io/blob/master/projection-screen.JPG)
## Configuration viewer.js
```javascript    
widgets {
    projection: {
        include: true,
        id: 'projection',
        type: 'titlePane',
        canFloat: true,
        position: 10,
        path: 'gis/dijit/Projection',
        title: 'Projections',
        options: {
            map: true,
            mapClickMode: true,
            // optionally specify local projection files location {SRID}.js
            // proj4BaseURL: '/local/projections'
            projectionList: [
                { title: 'NAD27', srid: 2029 },
                { title: 'WGS84', srid: 4167 }
            ]
        }
    }
}
```
## Usage
Click on the target icon (this is a toggle for choosing a location), then click on the map. This will display a crosshair on the map as well as a grid of various coordinates (as entered in config) at that location. You can then click in another location and the grid will be updated.

Closing the widget will clear the grid and turn the location selection off (click mode).

**ZoomTo** will always recentre the Flag on the map (if one is there). 

Last, but not least. **All of the cells in the grid can be edited**. Simply enter/change a coordinate in any projection, and the flag will be moved, the map recentred and all coordinates updated.
