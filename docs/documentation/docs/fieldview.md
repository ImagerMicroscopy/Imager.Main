# Using the Field Viewer for Visualizing Large Areas

In addition to standard image processing tools, Imager provides support for basic tile scan visualization through the **Field Viewer** utility.  

When entering the Field Viewer, this is the default window you will see:

![Field Viewer](images\\fieldview.png)

You can now configure the Field Viewer for your acquisition.

---

## Setting up the Field Viewer

The Field Viewer can be used in **live** or **experiment** mode. To use it correctly, you need to know the **virtual pixel size** (in nanometers) of your final image.

<div style=\"background-color: #ffe5e5; border-left: 5px solid #ff4d4d; border-radius: 10px; padding: 15px; margin: 10px 0;\">
<strong>⚠️ Important:</strong>  
If the pixel size or camera orientation is incorrect, the tiling will not display correctly.
</div>

The virtual pixel size can be calculated as:

Pixel size (nm) = Physical camera pixel size / Total system magnification


### Input Fields

Once the pixel size is configured, you need to set the following:

- **Acquisition** – The name of the acquisition setting from which the data will be displayed  
- **Detector** – The name of the detector within that acquisition setting

**Example:**  

We are imaging live using the acquisition setting **Channel1**:

<img src="Channel1.png" alt="Acquisition example" width="350"/>

For **Channel1**, two detectors are enabled: **DummyCam1** and **DummyCam2**.  
In the Field Viewer, the options for acquisitions and detectors will appear as:

<img src="availablechannelsanddetectors.png" alt="Available channels and detectors" width="350"/>

Select the desired **Acquisition** and **Detector** from the dropdown menu, then press **Engage** to enable the update loop.

<div style="background-color: #f3e8ff; border-left: 5px solid #b366ff; border-radius: 10px; padding: 15px; margin: 10px 0;\">
<strong>📝 Note:</strong>  
- Each acquisition/detector pair has its own Field Viewer. Changing the selection from the dropdown switches the currently visible Field Viewer.  
- Even if a Field Viewer is not currently selected, it will continue updating in the background.
</div>

---

## Field Viewer Settings

Contrast for each Field Viewer can be adjusted independently by modifying the **minimum** and **maximum** displayed values in the top-right corner.  

Additional actions:

- **Clear view** – Clears all displayed images for all acquisition/detector pairs  
- **Reset view** – Resets the viewport to default transformations  
- **Go to current** – Centers the viewport on the current stage position

