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

## Deploy
