# Creation Kit Landscape Tools



Used to edit the local landscape in the render window.

To access this window, use the "**H**" hotkey from the Render Window. Only useful in exterior cells.

Hotkeys can be found on the **Landscape Hotkeys** Page.

- Height
  - **Edit Radius:** Controls size of the editing brush. Can also be controlled with "[" and "]".





- - **Edit Falloff %:** Controls the softness/hardness of the edge of the editing brush. Can also be controlled with "Shift + [" and "Shift + ]".
  - **Flatten Vertices:** When checked; Brush will flatten terrain.
  - **Soften Vertices:** When checked; Brush will soften terrain variation.
  - **Show Edit Radius:** When checked; Brush Radius appears in the Render Window.

- Drawing Mode

   

  When in Drawing mode, holding down Left-Click will sculpt terrain changes wherever the cursor is moved.

  - **Value Field:** Specify in positive or negative [units](https://www.creationkit.com/index.php?title=Unit) the value for various Drawing Modes.
  - **Raise To/By:** Raises terrain at or below the initially clicked terrain height by the number of [units](https://www.creationkit.com/index.php?title=Unit) specified in the Value Field.
  - **Lower To/By:** Lowers terrain at or above the initially clicked terrain height by the number of [units](https://www.creationkit.com/index.php?title=Unit) specified in the Value Field.
  - **Delta:** Increase/Decrease height by Value Field amount.
  - **Absolute Height:** Used with Raise To and Lower To to set the landscape height to the value specified in the Value Field.

- Texture

   

  Used to specify the texture to paint when Right-Clicking during normal edit mode.

  - **Texture List:** List of available Textures by ID and Filename 
    To add or change textures, go the the Object Window. Textures are under Miscellaneous/Land Texture.
  - **Selected Texture:** Preview of Currently Selected Texture.
  - **Max Opacity:** Controls Strength of brush when painting texture.
  - **Applying Textures:** Right click on the terrain to apply the selected texture. "Ctrl + Right-Click" in the render window to select a texture already applied to the heightmap.



- Vertex Color:

   

  Clicking the Edit Colors checkbox switches to Color Painting Mode. This allows painting of color tints on the heightmap vertices.

  - **RGB:** Manual entry of Left/Right-click Shading colors.
  - **Select Color:** Select shading shading colors from palette menu.
  - **Rows of color Swatches**: Two rows of swatches to store custom colors.
  - **Edit Colors:** Toggle Vertex Color Paint Mode.

------

Origin: https://www.creationkit.com/index.php?title=Landscape