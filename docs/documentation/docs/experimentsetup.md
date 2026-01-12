# Setting up Experiments

This section provides all resources you need to start and configure an experiment.

---

## Starting an Experiment and Setting Storage Directories

To begin, add a new experiment by pressing **Add** on the **Experiments** tab.  
You can create multiple experiments and select the one you want to run. Once selected, its contents appear in the **Experiment Editor**:

<img src="experimentadded.png" alt="Experiment added" width="150"/>

By default, the first element is called **Root**. This element contains the storage location and file name settings.  
You can enable or disable storage (default is enabled) depending on whether you want to save your results.  
**Note:** The Root element **cannot be deleted**.

<img src="rootelement.png" alt="Root element settings" width="250"/>

---

## Adding and Re-arranging Elements

The **Experiment Editor** contains all elements that will be executed.  

- **Add an element:** Press **Add element**  
- **Delete an element:** Select it and press **Delete element**  
- **Reorder elements:** Drag them to a new position or inside other elements  

Elements nested inside another element will execute within that context.  

**Example 1:** A `DoTimes` loop containing a `Detection` and a `Wait`:

<img src="DoTimesWithWait.png" alt="DoTimes with wait" width="250"/>

This will execute a loop where each iteration waits 1 second before performing the detection.  

**Example 2:** A more complex workflow:

<img src="complexworkflow.png" alt="Complex workflow" width="250"/>

This workflow performs a **relative stage loop** (tile scan). At each position:  

1. Acquire a **time-lapse** of 100 images with ΔT = 0.01 s  
2. Acquire a **Z-stack** at that position  

**Important:** Only certain elements can contain child elements:

- Do Times  
- Relative Stage Loop  
- Stage Loop  
- Time Lapse  

<div style="background-color: #ffe5e5; border-left: 5px solid #ff4d4d; border-radius: 10px; padding: 15px; margin: 10px 0;">
<strong>⚠️ Important:</strong>  
A loop element must contain at least one child element. Otherwise, the program will not start.
</div>

---

## Available Elements

### Detection

The **Detection** element handles data acquisition.  
It **cannot have children**.  

When added, all user-defined acquisition settings are enabled by default.  
You can toggle each setting on or off. All enabled settings are applied sequentially.

<div style="background-color: #f3e8ff; border-left: 5px solid #b366ff; border-radius: 10px; padding: 15px; margin: 10px 0;"> 
<strong>📝 Note:</strong>  
If multiple cameras are selected, data will be acquired for each camera separately.
</div>

**Example:** GFP and Cy5 acquisition settings active

<img src="detection.png" alt="Detection example" width="350"/>

---

### Relative Stage Loop

A **Relative Stage Loop** defines a tile scan relative to the current position.  
It generates a grid in XYZ, with adjustable number of tiles and step size.  
The **Return to original position** option moves the stage back to the starting point after completion.

<img src="relstageloop.png" alt="Relative stage loop" width="350"/>

<div style="background-color: #f3e8ff; border-left: 5px solid #b366ff; border-radius: 10px; padding: 15px; margin: 10px 0;"> 
<strong>📝 Note:</strong>  
Stage axis orientation matters. If axes are flipped, the visual representation may not match actual stage movement. Take care with large tile scans.
</div>

---

### Stage Loop

Moves the stage to a set of predefined positions or specific XYZ coordinates.

<img src="stageloop.png" alt="Stage loop" width="350"/>

**Position List Actions:**

- **Add current position** – Adds the stage’s current coordinates  
- **Set to current position** – Overwrites the selected position with current coordinates  
- **Move up / Move down** – Reorder positions in the list  
- **Delete selected** – Remove a position  
- **Move stage to selected** – Move the stage to the chosen position  

Positions can also be loaded from templates. For example, a **96-well plate** (9 mm spacing):

<img src="96wellplate.png" alt="96-well plate positions" width="350"/>

Positions follow a **chessboard naming pattern**.

---

### Wait For Time

Pauses execution for a specified number of seconds.

<img src="Wait.png" alt="Wait element" width="350"/>

---

### Irradiation

Irradiates a sample using a selected light source for a defined duration.  
No data is acquired during irradiation.

**Example:** 20 seconds at 100% power on "ch1"

<img src="Irradiation.png" alt="Irradiation element" width="350"/>

---

### Do Times

A **Do Times** element acts as a for-loop.  
It repeats all child elements **N times**.

<img src="dotimes.png" alt="DoTimes element" width="350"/>

<div style="background-color: #f3e8ff; border-left: 5px solid #b366ff; border-radius: 10px; padding: 15px; margin: 10px 0;">
<strong>📝 Note:</strong>  

**Special case – Fast Acquisition Loop:**

<img src="fastacquisitionloop.png" alt="Fast acquisition loop" width="350"/>

DoTimes loops containing only **Detection** elements are converted internally into a **fast acquisition loop**.  

This communicates with the camera once to acquire all frames asynchronously, avoiding delays from repeated back-and-forth commands.  

⚠️ Adding other elements inside the loop disables this optimization.
</div>

---

### Time Lapse

Repeats all child elements with a predefined interval between repetitions.

<img src="timelapse.png" alt="Time lapse element" width="350"/>

---

### Update Acquisition

This element is used **only with smart microscopy workflows**.  
See [Setting up smart imaging pipelines](smartimaging.md) for details.

---

## Starting Your Experiment

Once the experiment tree is configured:

- Press **Start** at the top to begin execution  
- Use the scrollbar to navigate through the experiment (disable **Show last** or change pinned position as needed)  
- Press **Stop** to end the experiment  

---

## Next Steps

- [Setting up smart imaging pipelines](smartimaging.md)
