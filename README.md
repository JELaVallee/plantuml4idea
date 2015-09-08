plantuml4idea
=============


**Branch Notes**
==
**branch:**
jel-feature-misscache-on-render-error

**purpose:**

Currently, if the there is an error in rendering (as regularly occurs when the ToolWindow is being updated during an incomplete puml edit), then the zoom/scroll image cache is replaced with the green/red-on-black error image produced by the PlantUml rendering engine.  If you're working on a particularly large (e.g. larger than the visible display area of the PlantUML ToolWindow) this can cause for a jarring UX as the area a developer may be looking at/editing in the diagram suddenly disappears back to 0,0 origin.   

**methodology:**

Going to see if there is a way to capture the error state from the PlantUml rendering engine and block the rendering of the image... instead, display the error image in a bubble overlay over top the cached pre-error render state.  Clear the presentation of the error message when the next non-error image update occurs.

==



Intellij [IDEA plugin for PlantUML](http://plugins.intellij.net/plugin/?idea&id=7017)

This plugin provides integration with popular [PlantUML](http://plantuml.sourceforge.net/) diagramming tool

Author: [Eugene Steinberg](https://github.com/esteinberg)

Contributors:

 * [Ivan Mamontov](https://github.com/IvanMamontov)
 * [Henady Zakalusky](https://github.com/hza)
 * [Max Gorbunov](https://github.com/6zow)
 * [Vojtěch Krása] (https://github.com/krasa)

# Features

* PlantUML tool window renders PlantUML source code under caret in currently selected editor
* Supports multiple sources per file
* Supports pagination and zoom
* Can copy diagram to clipboard or export as PNG, EPS or SVG

# Tips

* Don't forget that @startuml tag is required.
* To be able to generate many diagram types, you must have [Graphviz](http://plantuml.sourceforge.net/graphvizdot.html)
 installed on your machine. About screen tests your installation.

# Developer notes

There are following branches:

### master
* Contains new experimental syntax support
* Grammar classes can be generated using tools/grammar-gen.sh
* This script can run automatically when you run the plugin using "Plugin" Run/Debug confuguration. Just add the script
above as an external tool and make it run before the "Make" step.

### 1.x 
* Current production branch
* No setup needed, checkout and run.
