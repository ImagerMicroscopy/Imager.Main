# GUI Overview

This section provides an overview of the graphical user interface (GUI) and its main panels.

---

## Panels Overview

The GUI consists of six main panels:

![GUI panel overview](images\guitaboverview.png)

1. **Acquisitions tab** – Configure hardware and acquisition settings. View user-defined acquisitions and individual hardware components.  
2. **Status tab** – Monitor the progress of measurements and the currently executing element.  
3. **Image view tab** – Main viewport for displaying acquired data. You can also switch to the Field View or Smart Program Editor.  
4. **Acquisition control tab** – Start live acquisition or run the currently selected experiment.  
5. **Experiment tab** – Create and manage experimental workflows.  
6. **Stage control** – Control the stage manually.

The following sections provide an in-depth guide for each panel.

---

## Acquisitions Tab

The **Acquisitions tab** is used to define settings for all hardware components.

![Acquisitions tab](images\acqtab.png)

### 1. User-Defined Acquisitions

Here you can define new acquisition settings. Press **Copy** to create a new setting based on an existing one.

<div style="background-color: #f3e8ff; border-left: 5px solid #b366ff; border-radius: 10px; padding: 15px; margin: 10px 0;">
<strong>📝 Note:</strong> Copying an acquisition setting duplicates all parameters from the source setting.
</div>

- Press **Remove** to delete an acquisition.  
- Each acquisition must have a unique, non-empty name. Special characters are not allowed.  
- The experiment will not start if duplicate names exist.

---

### 2. Available Light Sources

Displays all light sources grouped by equipment.  

**Enabling a light source:** Check the box next to the light source name.  
**Adjusting power:** Use the percentage slider (1–100%). If the slider is disabled, the setting is ignored.

---

### 3. Movable Components

Components can be **discrete** (e.g., filter wheel) or **continuous** (e.g., stepper motor).  
Hover over numeric inputs to see the allowed range for continuous components.

<div style="background-color: #ffe5e5; border-left: 5px solid #ff4d4d; border-radius: 10px; padding: 15px; margin: 10px 0;">
<strong>⚠️ Important:</strong> Values exceeding the allowed range are clamped to the minimum or maximum.
</div>

Each movable component must have a setting selected.

---

### 4. Toggle Detectors

Imager supports multiple cameras (limited by data throughput).  
You can toggle each camera on or off during acquisition.

---

### 5. Detector Properties

Adjust properties such as exposure time or cropping for each detector.

<div style="background-color: #ffe5e5; border-left: 5px solid #ff4d4d; border-radius: 10px; padding: 15px; margin: 10px 0;">
<strong>⚠️ Important:</strong> Detector settings are validated by applying and reading them back to avoid inconsistencies. Certain crop settings may not support requested exposure times.
</div>

---

## Status Tab

Displays the status of the current measurement and the active element.

---

## Image View Tab

The **Image View** panel displays data during live acquisition or experiment runs.

![Image view](images\imageview.png)

### 1. Contrast Settings

Adjust contrast via the slider or input box. Enable or disable **auto-contrast** as needed.

<div style="background-color: #f3e8ff; border-left: 5px solid #b366ff; border-radius: 10px; padding: 15px; margin: 10px 0;">
<strong>📝 Note:</strong> In <strong>multi-channel view<strong>, each channel has a double-slider for contrast. No histogram is displayed.
<br><br>

<img src="multichannelcontrast.png" alt="Multi-channel contrast" style="max-width: 50%; border-radius: 8px;">
</div>

---

### 2. Image Elements

Shows all overlay elements on the image.  
See [Live plotting and analysis tools](analysistools.md) for usage details.

---

### 3. Multi-Channel View

Configure and view up to 5 channels simultaneously (4 colors + 1 transmission).  
See [Multi-color display](multicolordisplay.md) for instructions.

---

### 4. Selected Position

Filter displayed data by a tagged stage position during an experiment. Useful for reviewing specific positions.

---

### 5. Scroll Bar

Acts as a **time axis** for scrolling through previously acquired data.

<div style="background-color: #f3e8ff; border-left: 5px solid #b366ff; border-radius: 10px; padding: 15px; margin: 10px 0;">
<strong>📝 Note:</strong>  
The displayed time index corresponds to the execution of **Detection** elements in the experiment tree, not raw TIFF frames. If multiple cameras or acquisitions are used in one Detection element, scrolling may advance multiple images at once.
</div>

---

### 6. Reset View

Resets all zoom and translation transformations applied by the user.

---

### 7. Toolbar

Contains image analysis tools and the multi-channel view toggle.  
See [Live plotting and analysis tools](analysistools.md) for a detailed guide.

---

## Experiment Editor

The **Experiment Editor** allows editing and configuring experimental workflows.

![Experiment editor](images\experimenteditor.png)

### 1. Experiment List

Shows all available experiments.  
You can add, remove, save, or load experiments from a file.  
The currently selected experiment executes when **Start** is pressed. By default, no experiments exist.

---

### 2. Experiment Editor

Edit your workflow by adding or removing elements.  
See [Setting up your experiment](experimentsetup.md) for a detailed guide.

---

### 3. Selected Element Settings

Displays settings for the currently selected element.  
More details about element types are available at [Setting up your experiment](experimentsetup.md).

---

## Next Steps

After familiarizing yourself with the GUI, proceed to:

- [Setting up your experiment](experimentsetup.md)  
- [Live plotting and analysis tools](analysistools.md)  
- [Setting up smart imaging pipelines](smartimaging.md)  
- [Using the field viewer](fieldview.md)
