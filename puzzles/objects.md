# Objects

The puzzles from this category perform various operations with objects.

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-objects.jpg)

**"show"**

Makes a specified object, that was initially or previously hidden, visible. Also works for a list of objects, a group \(or a list of groups\) or with the [all objects](https://www.soft8soft.com/docs/manual/en/puzzles/Selectors.html#all_objects) puzzle.

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-object-show.jpg)

**"hide"**

Makes a specified object invisible. Also works for a list of objects, a group \(or a list of groups\) or with the [all objects](https://www.soft8soft.com/docs/manual/en/puzzles/Selectors.html#all_objects) puzzle.

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-object-hide.jpg)

**"is visible"**

Checks if an object \(or any of objects in a list\) is currently visible. If it so, returns true, otherwise returns false.

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-object-is-visible.jpg)

**"get objects from"**

This universal puzzle allows you to:

* get the list of objects contained in a group thus making it iterable
* convert the output of the **all objects** puzzle to a list thus making it iterable
* get children of some parent object

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-object-get-objects.jpg)

By using the dropdown you can also filter off objects of a kind \(e.g. cameras, lamps, annotations, etc\).

**"clone"**

Makes an object copy, generates a unique name for the new object and immediately adds it to the scene. Outputs the new object. Does not work with lists, groups or the [all objects](https://www.soft8soft.com/docs/manual/en/puzzles/Selectors.html#all_objects) puzzle.

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-object-clone.jpg)

**"snap to object"**

Moves an object to the position of another object by copying its transform data. Also copies rotation and scale. Does not work with lists, groups or the [all objects](https://www.soft8soft.com/docs/manual/en/puzzles/Selectors.html#all_objects) puzzle.

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-object-snap.jpg)

**"set transform"**

Moves, rotates or scales an object according to specified transform data. The "offset" checkbox enables moving/rotating/scaling an object relatively to the original position/rotation/scale. Any of the axis inputs can be left blank. Also works for a list of objects, a group \(or a list of groups\) or with the [all objects](https://www.soft8soft.com/docs/manual/en/puzzles/Selectors.html#all_objects) puzzle.

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-object-set-transform.jpg)

**"get transform"**

Retrieves the position, rotation or scale data of an object. Does not work with lists, groups or the [all objects](https://www.soft8soft.com/docs/manual/en/puzzles/Selectors.html#all_objects) puzzle.

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-object-get-transform.jpg)

**"change local transform"**

Moves, rotates or scales an object according to specified transform data in its local space. Any of the axis inputs can be left blank. Also works for a list of objects, a group \(or a list of groups\) or with the [all objects](https://www.soft8soft.com/docs/manual/en/puzzles/Selectors.html#all_objects) puzzle.

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-object-change-local-transform.jpg)

**"get object direction"**

Returns an object's direction vector or numeric **X**,**Y**,**Z** vector components.

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-object-get-object-direction.jpg)

**"add annotation"**

Add a 2D marker to an object that a user can expand by clicking on it to see the object description. Also works for a list of objects, a group \(or a list of groups\) or with the [all objects](https://www.soft8soft.com/docs/manual/en/puzzles/Selectors.html#all_objects) puzzle.

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-object-add-annotation.jpg)

**"remove annotation"**

Removes a previously added annotation from an object. Also works for a list of objects, a group \(or a list of groups\) or with the [all objects](https://www.soft8soft.com/docs/manual/en/puzzles/Selectors.html#all_objects) puzzle.

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-object-remove-annotation.jpg)

**"open annotation"**

Expands an annotation specified by its label.

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-object-open-annotation.jpg)

**"close annotation"**

Closes an annotation specified by its label.

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-object-close-annotation.jpg)

**"update text object"**

Generates a new mesh for a text object according to specified textual content. Also works for a list of objects, a group \(or a list of groups\) or with the [all objects](https://www.soft8soft.com/docs/manual/en/puzzles/Selectors.html#all_objects) puzzle.

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-object-update-text.jpg)

**"parent"**

Creates a parent relation between objects, so that the first object follows position/rotation/scale of the second one. Does not work with lists, groups or the [all objects](https://www.soft8soft.com/docs/manual/en/puzzles/Selectors.html#all_objects) puzzle.

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-object-parent.jpg)

**"distance"**

Outputs the distance between two specified objects. Does not work with lists, groups or the [all objects](https://www.soft8soft.com/docs/manual/en/puzzles/Selectors.html#all_objects) puzzle.

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-object-distance.jpg)

**"outline"**

Applies or removes the outline effect to/from a specified object. To unlock this puzzle, enable the outline effect in 3ds Max or Blender. Also works for a list of objects, a group \(or a list of groups\) or with the [all objects](https://www.soft8soft.com/docs/manual/en/puzzles/Selectors.html#all_objects) puzzle.

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-object-outline.jpg)

**"get custom props"**

Returns a [dictionary](https://www.soft8soft.com/docs/manual/en/puzzles/Dictionaries.html) with custom properties assigned to an object.

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-object-get-custom-props.jpg)

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-object-get-custom-props-example2.jpg)

Custom properties can be assigned in 3ds Max via the **User Defined Properties** panel, or in Blender by using the **Custom Properties** panel.

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-object-get-custom-props-example.jpg)

