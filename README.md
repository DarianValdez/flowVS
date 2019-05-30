# flowVS
Visual Studio Solution of StatesTitle/flow

# flow
Converts a title insurance workflow from ResWare's db into Graphviz's dot language and renders it with [Graphviz](https://graphviz.gitlab.io/).

* [database.py](database.py) connects to a SQL Server database, either directly or through an SSH
  tunnel
* [resware_model.py](resware_model.py) loads ResWare's ActionList information from its db
* [graph.py](graph.py) turns the ResWare information loaded in resware_model into a connected graph
  and converts that to dot
* [web.py](web.py) Loads the graph from the db, converts it to SVG with dot, and serves that as a web page

## Develop

1. Install GraphViz
1. Update DOT_EXE_PATH in settings.py to point to dot.exe int the Graph Viz installation folder:
  
    DOT_EXE_PATH = 'C:\\\\Program Files (x86)\\\\Graphviz2.38\\\\bin\\\\dot.exe'
1. Set variables in the .env file
1. Right-click on the python environment and choose 'Insall From requirements.txt'
1. Right-click on web.py and select 'Set as start-up file'

## Deploy
To deploy as an executable that can be run from anywhere:
1. Right-click on the flowVS project in Solution Explorer
1. Choose 'Open Command Prompt Here'
1. Enter the command:

    pyinstaller -n \[NAME\] web.py
    
    Where \[NAME\] is what you want the executable to be called.
1. Once it finishes building, you can find the built project in /flowVS/dist/ under the name you chose.
1. Copy this whole folder to the location you need, just run the \[NAME\].exe in the folder.
