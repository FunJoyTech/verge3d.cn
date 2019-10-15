# Materials

The puzzles from this category perform various operations with materials and textures.

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-materials.jpg)

### **"assign material"**

Assigns a material to an object, completely replacing the old material. Also works for a list of objects, a group \(or a list of groups\) or with the [all objects](https://www.soft8soft.com/docs/manual/en/puzzles/Selectors.html#all_objects) puzzle.

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-materials-assign-material.jpg)

[\#](https://www.soft8soft.com/docs/manual/en/puzzles/Materials.html#replace_texture)

### **"replace texture"**

Replaces a texture found for a specified material with the one loaded from the provided URI.

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-materials-replace-texture.jpg)

### **"set color"**

Set R, G and B components of a color parameter found for a specified material.

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-materials-set-color.jpg)

**For 3ds Max users:** you can add **Controllers** in your materials \(standard or physical\) and their names will be shown in the dropdown menu. In addition, diffuse \(or "base"\) color inputs for standard or physical material nodes are also accessible. In case of **glTF-compliant PBR** materials the **Base Color** and **Emission** inputs are only accessible with this puzzle.

**For Blender users:** you can add **RGB** nodes in your node-based materials \(GLSL Internal, Cycles, Eevee\) and their names will be shown in the dropdown menu. In addition, diffuse \(or "base"\) color inputs for Material, Extended Material, BSDF Principled, BSDF Diffuse and BSDF Glossy nodes are also accessible. In case of **glTF-compliant PBR materials** the **BaseColor** and **Emissive** inputs are only accessible with this puzzle.

This puzzle can also be used to modify the environment shader. In the drop-down, the name of the environment shader starts with "Verge3D\_Environment".

For more information on materials available to Verge3D users, please refer to Material system overview chapters of this manual: [3ds Max](https://www.soft8soft.com/docs/manual/en/introduction/Material-System-Max.html), [Blender](https://www.soft8soft.com/docs/manual/en/introduction/Material-System-Blender.html).

[\#](https://www.soft8soft.com/docs/manual/en/puzzles/Materials.html#materials_set_value)

### **"set value"**

Set a value parameter found for a specified material.

![](https://www.soft8soft.com/docs/files/puzzles/puzzles-materials-set-value.jpg)

**For 3ds Max users:** you can add **Controllers** in your materials \(standard or physical\) and their names will be shown in the dropdown menu. In case of **glTF-compliant PBR** materials the following inputs are accessible with this puzzle: Metalness, Roughness, Bump Scale, Emissive Intensity and Environment Map Intensity.

**For Blender users:** you can add **Value** nodes in your node-based materials \(GLSL Internal, Cycles, Eevee\) and their names will be shown in the dropdown menu. In case of **glTF-compliant PBR** materials the following inputs are accessible with this puzzle: metalness \(MetallicFactor in PBR node\), roughness \(RoughnessFactor in PBR node\), bumpScale \(NormalScale in PBR node\), emissiveIntesity \(EmissiveFactor in PBR node\) and envMapIntensity \(not presented in PBR node\).

This puzzle can also be used to modify the environment shader. In the drop-down, the name of the environment shader starts with "Verge3D\_Environment".

For more information on materials available to Verge3D users, please refer to Material system overview chapters of this manual: [3ds Max](https://www.soft8soft.com/docs/manual/en/introduction/Material-System-Max.html), [Blender](https://www.soft8soft.com/docs/manual/en/introduction/Material-System-Blender.html).

[\#](https://www.soft8soft.com/docs/manual/en/puzzles/Materials.html#get_material)

### **"get material"**

Retrieves the name of a material assigned to an object. If multiple materials are assigned to the same object, returns the first one.![](https://www.soft8soft.com/docs/files/puzzles/puzzles-object-get-material.jpg)

