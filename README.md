CADapi.js : JavaScript APIs for CAD
==========

Develop CAD software in JavaScript. CADapi.js makes JavaScript in AutoCAD® (version 2010 to recent 2016), BricsCAD®, ZWCAD++, Autodesk® Revit® and Inventor® as easy to use as possible. Make different CAD software to use the same APIs.

JavaScript APIs for CAD should come with .NETScript which is downloadable at www.NetOnApp.com


**Documentation**

All the CADapi.js commands should start with $$$. The reason is $ is used by jQuery and $$ is used by the web browsers (IE, Chrome, Firefox...).

Select all entities in the model, return their ObjectId and generic properties (layer name, color...):

    var entities = $$$("model");

Select all layers in the current AutoCAD/BricsCAD/ZWCAD++ database:

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
    
Zoom extents:

    $$$().zoomExtents();
    
Register an event handler:

    $$$().addEvent("commandEnded", function () {
    	// Do extra work after the command is ended
    });
    
Remove an event handler:

    $$$().removeEvent("beginQuit");

More APIs and demos are in development...
