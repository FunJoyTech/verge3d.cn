# Scenes

The puzzles from this category perform loading/unloading operations with scenes.![](https://www.soft8soft.com/docs/files/puzzles/puzzles-scenes.jpg)

[\#](https://www.soft8soft.com/docs/manual/en/puzzles/Scenes.html#load_scene)

**"load scene" + "percentage"**

When this puzzle is triggered, the current scene is unloaded and a new scene is loaded from a specified .gltf file. After loading is finished, the puzzles in the "when loaded do" slot are triggered. Also there can be enabled the "on progress do" slot. Puzzles placed in this slot are continuously triggered during the loading and can utilize the "percentage" puzzle.![](https://www.soft8soft.com/docs/files/puzzles/puzzles-scenes-load-scene.jpg)![](https://www.soft8soft.com/docs/files/puzzles/puzzles-scenes-load-scene-example.jpg)

[\#](https://www.soft8soft.com/docs/manual/en/puzzles/Scenes.html#append_scene)

**"append scene" + "percentage"**

When this puzzle is triggered, a new scene is loaded from a specified .gltf file and appended to the current scene. After loading is finished, the puzzles in the "when loaded do" slot are triggered. Also there can be enabled the "on progress do" slot. Puzzles placed in this slot are continuously triggered during the loading and can utilize the "percentage" puzzle. The "append scene" puzzle doesn't load cameras and lights from a new scene by default. This behavior can be changed in the puzzle's options.![](https://www.soft8soft.com/docs/files/puzzles/puzzles-scenes-append-scene.jpg)![](https://www.soft8soft.com/docs/files/puzzles/puzzles-scenes-append-scene-example.jpg)

[\#](https://www.soft8soft.com/docs/manual/en/puzzles/Scenes.html#unload_scene)

**"unload scene"**

Unloads the specified scene or its part from the application. Use the empty text value in order to unload all scenes.![](https://www.soft8soft.com/docs/files/puzzles/puzzles-scenes-unload-scene.jpg)

[\#](https://www.soft8soft.com/docs/manual/en/puzzles/Scenes.html#enable_rendering)

**"enable rendering"**

Resumes previously disabled rendering.![](https://www.soft8soft.com/docs/files/puzzles/puzzles-scenes-enable-rendering.jpg)

[\#](https://www.soft8soft.com/docs/manual/en/puzzles/Scenes.html#disable_rendering)

**"disable rendering"**

Disables rendering. The graphics won't be updated but the user events will be captured and animation timelines will progress.![](https://www.soft8soft.com/docs/files/puzzles/puzzles-scenes-disable-rendering.jpg)

You can use disable rendering for the purpose of saving batteries on mobile devices or laptops, and getting rid of cooler noise on desktops. You can also use it together with the **supersamping** puzzle to significantly increase the rendering quality and compensate the loss of performance.![](https://www.soft8soft.com/docs/files/puzzles/puzzles-scenes-enable-disable-rendering-example.jpg)

