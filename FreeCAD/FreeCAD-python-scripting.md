# FreeCAD python scripting

- Access
  - immediate execution on return : `View → Panels → Python Console`
  - scripting : `Macro → Macros → Create`
  - `Edit > Preferences > Python > Macro > Show script commands in Python console`
    - logs Python commands for GUI actions
- Naming conventions
  - `function()`
  - `Attribute`
  - `_internal_function()`
- Basic usage
  - ```py
    doc = FreeCAD.newDocument()
    print(doc.CreationDate)
    box = doc.addObject("Part::Box", name="myBox")
    doc.recompute()
    ```

  - ```py
    doc = App.ActiveDocument()
    doc.supportedTypes()
    parts_list = Gui.Selection.getSelection()
    box=parts_list[0]
    box.Height=20
    box.ViewObject.LineColor
    ```

  - ```py
    del_list = Gui.Selection.getSelection()
    for obj in del_list:
      doc.removeObject(obj.Name)
    ```

- Autocomplete
  - `doc.`
  - `box.`

- Vectors
  - widely-used for manipulating objects
    - distances
    - angles
    - relations
  - ```py
    vec1 = FreeCAD.Vector(2, 0, 0)
    print(vec1)
    print(vec1.x)
    print(vec1.y)
    vec2 = FreeCAD.Vector(0, 3, 0)
    sum_vec1_vec2 = vec1.add(vec2)
    ```
- Placements
  - ```py
    print(box.Placement)
    print(box.Placement.Base)
    box.Placement.Base = sumvec
    ```

  - ```py
    placement1 = FreeCAD.Placement()
    placement1.Base = FreeCAD.Vector(5, 5, 0)
    box.Placement = placement1
    ```
- Parts workbench
  - shapes v. document objects
    - shapes : geometry
    - document objects : "shape container"

  - ```py
    # create shapes
    import Part
    boxShape = Part.makeBox(3,5,7)
    myObj = FreeCAD.ActiveDocument.addObject("Part::Feature","MyNewBox")
    myObj.Shape = boxShape
    FreeCAD.ActiveDocument.recompute()
    ```

  - ```py
    # print shape properties
    print(boxShape.Vertexes)
    print(boxShape.Edges)
    print(boxShape.Wires)
    print(boxShape.Faces)
    print(boxShape.Shells)
    print(boxShape.Solids)

    for f in boxShape.Faces:
      print(f.Area)

    for e in boxShape.Edges:
      print("Edge :")
      print("Start point-")
      print(e.Vertexes[0].Point)
      print("End point-")
      print(e.Vertexes[1].Point)

    print(boxShape.ShapeType)
    print(boxShape.Faces[0].ShapeType)
    print(boxShape.Vertexes[2].ShapeType)
    ```
- resources
  - <a href="https://wiki.freecad.org/Manual:Creating_and_manipulating_geometry" target="_blank">practice : creating a simple geometry</a>
  - <a href="https://wiki.freecad.org/Topological_data_scripting" target="_blank">parts scripting : official guide</a>