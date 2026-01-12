# Multi-Channel Display

Imager supports flexible multi-channel visualization. Each **Acquisition/Detector** pair from a **Detection** element in the experiment tree can be assigned to a channel in the Multi-Channel view.  
Up to **5 channels** are available (4 colors + 1 grayscale).

---

## Attaching Data to a Channel

When you first open the Multi-Channel view, you will see an empty panel:

<img src="multichannelview.png" alt="Multi-channel view initial state" width="250px" style="border-radius: 8px;">

Let’s create an example experiment with **2 acquisition settings**: GFP and Cy5. Both are available in the experiment tree:

<img src="gfpcy5.png" alt="Example experiment with GFP and Cy5" width="250px" style="border-radius: 8px;">

<div style="background-color: #f3e8ff; border-left: 5px solid #b366ff; border-radius: 10px; padding: 15px; margin: 10px 0;">
<strong>📝 Note:</strong>  
You can use the Multi-Channel view in <strong>live mode<strong> (without storing data) by turning off the <strong>Save output?<strong> option in the Root element.
</div>

---

### Adding Channels

1. Press the **Add** button next to the channels you want to activate.  
   Example: activate the green and red channels:

   <img src="redgreenactive.png" alt="Green and red channels active" width="250px" style="border-radius: 8px;">

2. Press the `+` button to bind the channel to your experiment. You will be redirected to the experiment tree.  
   - Double-tap the **Detection** element you want to bind  
   - Select the corresponding acquisition setting and detectors

   <img src="binding.png" alt="Binding acquisition to channel" width="250px" style="border-radius: 8px;">

---

### Using the Multi-Channel View

- Toggle the Multi-Channel view using the button on the left:

  <img src="buttonmultichannel.png" alt="Toggle multi-channel view button" width="150px" style="border-radius: 8px;">

- To clear channels, press **Remove** next to the corresponding channel.

Once enabled, the multi-channel view will display all assigned channels.  
Example for Dummy Cameras:

<img src="multichannelfull.png" alt="Multi-channel view with multiple cameras" width="450px" style="border-radius: 8px;">
