# GraphViz
[![license](https://img.shields.io/github/license/mashape/apistatus.svg?maxAge=2592000)](https://github.com/ranjaykrishna/GraphViz/blob/master/LICENSE)

Visualizes a graph stored as a json file as a force-directed graph in a webbrowser. It has specifically been built to visualize scene graphs, a representation commonly used in computer vision. See [Visual Genome](https://visualgenome.org) for details about the representation.

This type of visualization is often found in many computer vision papers that build models to display their model's output scene graphs.


![example image](https://cs.stanford.edu/people/rak248/VG_100K_2/1.jpg) ![example scene graph](https://github.com/ranjaykrishna/GraphViz/blob/master/example_scene_graph.png)


### Usage
First, you need an image and its associated scene graph.

Save a scene graph object as json in a file with the following format:
```
{
    url: STRING,
    objects: [
        {name: STRING},
        ...
    ],
    attributes: [
        {attribute: STRING, object: INT},
        ...
    ],
    relationships: [
        {predicate: STRING, object: INT, subject: INT},
        ...
    ]
}
```
The url should point to an image source. The attributes and relationships lists contain an `object` int field that is an index to the object it refers to in the objects list.

Run the following command to visualize the scene graph:
```
python visualize_scene_graph.py --graph LOCATION_OF_YOUR_SCENE_GRAPH
```
The above command will automatically open up the browser and display a scene graph and its associated image.

### Contributing.
Feel free to contribute to this project by sending me a pull request. Feel free to follow me on twitter (@RanjayKrishna) for updates and to see my other work.
