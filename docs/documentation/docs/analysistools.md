# Live Plotting and Analysis Tools

A small set of live plotting and analysis tools is available during data acquisition.  
These tools are pinned to the toolbar on the **left side of the main image display**.

![Toolbar](images/toolbar.png)

## Available Tools

<div>
<img src="dot.png" alt="Circular area selection icon" width="50"/>
<strong> Circular Area Selection</strong><br>
Measures the <strong>mean</strong>, <strong>maximum</strong>, and <strong>minimum</strong> intensity within a selected circular region of the image.
<br>
Use <strong>Ctrl + +</strong> to increase the circle size and <strong>Ctrl + -</strong> to decrease it.
</div>

<br>

<div>
<img src="linetool.png" alt="Line profile icon" width="50"/>
<strong> Line Profile</strong><br>
Plots the intensity profile along a line drawn across the image.
<br>
Use <strong>Ctrl + +</strong> to increase the line thickness and <strong>Ctrl + -</strong> to reduce it.
</div>

---

## Using the Area Tool

1. **Select an image**  
   Double-tap the image you want to analyze.  
   A faint aquamarine border will appear, indicating that the image is active.

   <img src="border.png" alt="Selected image border" width="50"/>

2. **Activate the area tool**  
   Click the <strong>Circular Area Selection</strong> button.  
   A red indicator dot will appear in the top-left corner of the image.

   <img src="dotstart.png" alt="Area tool activated" width="50"/>

3. **Place circular regions**  
   Move the cursor over the image and adjust the region size using  
   <strong>Ctrl + +</strong> or <strong>Ctrl + -</strong>.  
   Click once to place a circular region.  
   Multiple regions can be added before confirming.

   <img src="multiregions.png" alt="Multiple circular regions" width="150"/>

4. **Confirm the selection**  
   Press <strong>Enter</strong> to finalize the selection.

---

## Using the Line Tool

1. **Select an image**  
   Double-tap the image to activate it.  
   A faint aquamarine border will appear.

2. **Draw the line**  
   Move the cursor to the desired starting position and click once.  
   Move the cursor to the end position and click again to complete the line.

   <img src="linedrawn.png" alt="Line drawn on image" width="150"/>

3. **Confirm the selection**  
   Additional lines may be added if required.  
   Press <strong>Enter</strong> to finalize the selection.

---

## Plotting Data

After confirming a selection, a new <strong>collection ID</strong> appears in the  
<strong>Image Elements</strong> tab.

<img src="elementcollection.png" alt="Element collection list" width="350"/>

Each collection represents a group of selected elements.  
The following actions are available:

- <strong>Plot</strong><br>
  Generates plots for all elements across all collections.

- <strong>Hide / Show all</strong><br>
  Toggles the visibility of all analysis overlays on the images.

- <strong>Delete</strong><br>
  Removes the selected collection.

<div style="background-color: #f3e8ff; border-left: 5px solid #b366ff; border-radius: 10px; padding: 15px; margin: 10px 0;">
<strong>📝 Note:</strong><br>
Plots are generated separately for each <strong>Acquisition / Detector</strong> pair.
</div>

---

## Viewing Plots

Pressing <strong>Plot</strong> opens a new window displaying the generated plots.

<img src="plots.png" alt="Plots window" width="350"/>

Plot windows can be closed at any time.  
To display them again, simply press <strong>Plot</strong>.
