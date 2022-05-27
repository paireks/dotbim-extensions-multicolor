# dotbim-extensions-multicolor (Version 1.0.0)

## Introduction

Extension for dotbim file format to allow multicolor elements.

Idea of multicolor elements was introduced by Viktor Kovacs - https://github.com/paireks/dotbim/issues/11

Main repository for dotbim: https://github.com/paireks/dotbim
dotbim website: https://dotbim.net/

## Tag

To color single element with multiple colors add "face_colors" tag inside an element.
"face_colors" is a simple list of integers (integers should be between 0-255) organised in that way:

[r1, g1, b1, a1, r2, g2, b2, a2, r3, g3, b3, a3, ... rn, gn, bn, an]

It should match each face of the mesh.

So let's say you have 3 faces inside one mesh, and wanted to color first face (triangle) as red (255,0,0,255), second as skyblue (135,206,235,255), third as white (255,255,255,255).
Then you will have:

```json

"face_colors" : [ 255, 0, 0, 255, 135, 206, 235, 255, 255, 255, 255, 255 ]

```

## Example

```json

{
  "schema_version": "1.0.0",
  "meshes": [
    {
      "mesh_id": 0,
      "coordinates": [ 0.0, 0.0, 0.0, 1.0, 0.0, 0.0, 1.0, 1.0, 0.0, 0.0, 1.0, 0.0 ],
      "indices": [ 0, 1, 2, 0, 2, 3 ]
    }
  ],
  "elements": [
    {
      "mesh_id": 0,
      "vector": { "x": 0.0, "y": 0.0, "z": 0.0},
      "rotation": { "qx": 0.0, "qy": 0.0, "qz": 0.0, "qw": 1.0 },
      "guid": "9f61b565-06a2-4bef-8b72-f37091ab54d6",
      "type": "Brick",
      "color": { "r": 255, "g": 0, "b": 0, "a": 255 },
      "face_colors" : [ 255, 0, 0, 255, 0, 255, 0, 255 ],
      "info": {
        "Name": "Colored Element"
      }
    }
  ],
  "info": {
    "Author": "Viktor Kovacs"
  }
}

```
