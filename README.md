CADapi.js : JavaScript APIs for CAD
==========

Develop CAD software in JavaScript. CADapi.js makes JavaScript in AutoCAD® (version 2010 to recent 2016), BricsCAD®, ZWCAD, Autodesk® Revit® and Inventor® as easy to use as possible. Make different CAD software to use the same APIs.

JavaScript APIs for CAD should come with .NETScript which is downloadable at www.NetOnApp.com


**Documentation**

All the CADapi.js commands starts with $$$. The reason is $ is used by jQuery and $$ is used by the web browsers (IE, Chrome, Firefox...). CADapi.js works together with all JavaScript libraries inside its web browser as the NetOnApp .NETScript plugin.

*Generic APIs across AutoCAD/BricsCAD/ZWCAD, Revit and Inventor:*

Select all entities in the model, return their Id and generic properties (layer name, color...):

    var entities = $$$("model");

Get all properties of an entity with its Id:

    var data = $$$(id); // id is handle ID (AutoCAD) or number ID (Revit)
    
Select an entity on the screen:

    $$$().select(id);

Update an entity with its id, propertyName and valueName

    $$$().update(id, propertyName, valueValue);

Zoom on the screen:

    $$$().zoomExtents();    // Zoom extents
    $$$().zoom(id, 2.5);    // Zoom with scale

Register an event handler:

    $$$().addEvent("commandEnded", function () {
    	// Do extra work after the command is ended
    });
    
Remove an event handler:

    $$$().removeEvent("beginQuit");

*AutoCAD/BricsCAD/ZWCAD APIs specific:*

Select all layers in the current AutoCAD/BricsCAD/ZWCAD database:

    var layers = $$$("layer");

Select all lines, with their most used properties in a JavaScript array object:

    var lines = $$$("line");

Select all circles with specified radius:

    var circles = $$$("circle[radius=10]");

Update layer name of all blocks:

    $$$("block").update("layer", "0");

Get drawing variables:

    $$$("variable"); // Get all drawing variables
    $$$("variable['clayer']"); // Get current layer name

Set drawing variables:

    // Set current layer to layer 0
    $$$("variable").update("clayer", "0"); // Option 1
    $$$("variable['clayer']") = "0";       // Option 2

Run AutoCAD command:

    $$$().runCommand("LINE");
    
*Revit APIs specific:*

Get element property names and values

    var sheets = $$$("sheet");   // Get all sheets and return their properties
    var walls = $$$("wall");    // Get all walls and return their properties

General syntax with selector:

    var data = $$$("xxx");
    // xxx : areaScheme, areaTag, cableTray, casework, ceiling, column, communicationDevice, conduit, conduitFitting, curtainSystem, curtainWallMullion, dataDevice, detailComponent, door, ductCurve, ductAccessory, ductFitting, ductInsulation, ductLining, electricalEquipment, electricalFixture, entourage, fireAlarmDevice, flexDuctCurve, flexPipeCurve, floor, furniture, furnitureSystem, genericModel, hvacZone, lightingDevice, lightingFixture, mass, mechanicalEquipment, nurseCallDevice, parking, parts, pipeAccessory, pipeFitting, pipeInsulation, pipeCurve, planting, plumbingFixture, railing, ramp, road, roof, room, roomTag, revitLink, sectionBox, securityDevice, shaftOpening, site, specialityEquipment, sprinkler, stair, structuralColumn, structConnection, fabricArea, fabricReinforcement, structuralFoundation, structuralFraming, pathRein, rebar, structuralStiffener, truss, telephoneDevice, topography, wall, window

More APIs and demos are in development...
