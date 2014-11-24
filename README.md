CADapi.js : JavaScript APIs for CAD
==========

Develop CAD software in JavaScript, with different APIs from Autodesk® AutoCAD® JavaScript API. CADapi.js makes JavaScript in AutoCAD® (version 2010 to recent 2015), BricsCAD®, ZWCAD++ as easy to use as possible.

JavaScript APIs for CAD should come with .NETScript which is downloadable at www.NetOnApp.com


**Documentation**

Select all layers in the current AutoCAD/BricsCAD/ZWCAD++ database:

    var layers = db("layer");

Select all lines:

    var lines = db("line");

Select all circles with specified radius:

    var circles = db("circle[radius=10]");

Update layer name of all blocks:

    db("block").update("layer", "0");

Run AutoCAD command:

    db().runCommand("LINE");
    
Zoom extents:

    db().zoomExtents();

Register an event handler:

    db().addEvent("commandEnded", function () {
    	// Do extra work after the command is ended
    });
    
Remove an event handler:

    db().removeEvent("beginQuit");

More APIs and demos are in development...
