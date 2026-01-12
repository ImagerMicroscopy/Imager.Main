# Smart Program API

## Input and exposed parameters

<!-- Start of HTML block -->
<div class="equipment-parameter" style="font-family: Arial, sans-serif; line-height:1.3; border:3px solid #2196F3; border-radius:6px; overflow:hidden; margin-top:1em;">

  <!-- Top header strip -->
  <div style="background-color:#2196F3; color:white; padding:0.4em 0.8em; font-weight:bold; font-size:1.1em;">
    EquipmentParameter
  </div>

  <!-- Content -->
  <div style="padding:0.8em;">

    <p style="margin-top:0; margin-bottom:0.5em;">
      Represents a modifiable equipment parameter derived from an acquisition update.
    </p>

    <section class="attributes" style="margin-bottom:0.5em;">
      <h3 style="margin-bottom:0.2em; font-size:1em;">Attributes</h3>
      <ul style="margin-top:0; margin-bottom:0.5em; padding-left:1.2em;">
        <li>
          <strong>value</strong> <em>(Any)</em><br>
          The current value of the equipment parameter. This can be read or updated to modify the parameter.
        </li>
      </ul>
    </section>

    <section class="usage" style="margin-bottom:0.5em;">
      <h3 style="margin-bottom:0.2em; font-size:1em;">Usage</h3>
      <h4 style="margin-bottom:0.2em; font-size:0.95em;">Modifying Acquisition Parameter</h4>
      <pre style="margin:0; padding:0.5em; background-color:#f7f7f7; border-radius:4px;"><code class="python">
# Assuming `equipment_param` is an instance of EquipmentParameter

# Read the current value
current_value = equipment_param.value
print("Current value:", current_value)

# Modify the value
equipment_param.value = 42  # set to a new value
print("Updated value:", equipment_param.value)
      </code></pre>
    </section>

  </div>
</div>


<div class="api-documentation" style="font-family: Arial, sans-serif; line-height:1.3; border:3px solid #2196F3; border-radius:6px; overflow:hidden; margin-top:1em;">

  <!-- Top header strip -->
  <div style="background-color:#2196F3; color:white; padding:0.5em 0.8em; font-weight:bold; font-size:1.2em;">
    ExposedParameterBase & Related Classes
  </div>

  <!-- Content -->
  <div style="padding:0.8em;">

    <h2 style="margin-bottom:0.2em;">ExposedParameterBase</h2>
    <p style="margin-top:0; margin-bottom:0.5em;"><em>Base class for all exposed parameters.</em></p>

    <section class="attributes" style="margin-bottom:0.5em;">
      <h3 style="margin-bottom:0.2em; font-size:1em;">Attributes</h3>
      <ul style="margin-top:0; margin-bottom:0.5em; padding-left:1.2em;">
        <li><strong>value</strong> <em>(float | int | bool | str | bytes)</em> – The raw value of the parameter.</li>
        <li><strong>annotation</strong> <em>(str)</em> – Descriptive annotation for the parameter.</li>
        <li><strong>type</strong> <em>(str)</em> – Type of the parameter (e.g., Scalar, Boolean).</li>
        <li><strong>variable</strong> <em>(str | None)</em> – Optional variable name associated with the parameter.</li>
      </ul>
    </section>

    <section class="methods" style="margin-bottom:0.5em;">
      <h3 style="margin-bottom:0.2em; font-size:1em;">Methods</h3>
      <ul style="margin-top:0; margin-bottom:0.5em; padding-left:1.2em;">
        <li><strong>serialize(name: str) → dict</strong> – Serialize the parameter and bind it to a variable name.</li>
        <li><strong>__repr__() → Any</strong> – Returns the raw parameter value.</li>
      </ul>
    </section>

    <hr style="margin:0.5em 0; border-color:#2196F3;">

    <h2 style="margin-bottom:0.2em;">Scalar</h2>
    <p style="margin-top:0; margin-bottom:0.5em;"><em>Floating-point scalar parameter.</em></p>
    <ul style="margin-top:0; margin-bottom:0.5em; padding-left:1.2em;">
      <li><strong>value</strong> <em>(float)</em></li>
      <li><strong>annotation</strong> <em>(str)</em></li>
      <li><strong>type</strong> <em>(str)</em> – default: <code>"Scalar"</code></li>
      <li><strong>variable</strong> <em>(str | None)</em></li>
    </ul>

    <hr style="margin:0.5em 0; border-color:#2196F3;">

    <h2 style="margin-bottom:0.2em;">Boolean</h2>
    <p style="margin-top:0; margin-bottom:0.5em;"><em>Boolean parameter.</em></p>
    <ul style="margin-top:0; margin-bottom:0.5em; padding-left:1.2em;">
      <li><strong>value</strong> <em>(bool)</em></li>
      <li><strong>annotation</strong> <em>(str)</em></li>
      <li><strong>type</strong> <em>(str)</em> – default: <code>"Boolean"</code></li>
      <li><strong>variable</strong> <em>(str | None)</em></li>
    </ul>

    <hr style="margin:0.5em 0; border-color:#2196F3;">

    <h2 style="margin-bottom:0.2em;">Integer</h2>
    <p style="margin-top:0; margin-bottom:0.5em;"><em>Integer parameter.</em></p>
    <ul style="margin-top:0; margin-bottom:0.5em; padding-left:1.2em;">
      <li><strong>value</strong> <em>(int)</em></li>
      <li><strong>annotation</strong> <em>(str)</em></li>
      <li><strong>type</strong> <em>(str)</em> – default: <code>"Integer"</code></li>
    </ul>

    <hr style="margin:0.5em 0; border-color:#2196F3;">

    <h2 style="margin-bottom:0.2em;">Text</h2>
    <p style="margin-top:0; margin-bottom:0.5em;"><em>Text (string) parameter.</em></p>
    <ul style="margin-top:0; margin-bottom:0.5em; padding-left:1.2em;">
      <li><strong>value</strong> <em>(str)</em></li>
      <li><strong>annotation</strong> <em>(str)</em></li>
      <li><strong>type</strong> <em>(str)</em> – default: <code>"Text"</code></li>
      <li><strong>variable</strong> <em>(str | None)</em></li>
    </ul>

    <section class="usage" style="margin-top:0.5em;">
      <h3 style="margin-bottom:0.2em;">Usage Example</h3>
      <pre style="margin:0; padding:0.5em; background-color:#f7f7f7; border-radius:4px;"><code class="python">
from parameters import Scalar, Boolean, Integer, Text

scalar_param = Scalar(value=3.14, annotation="Pi value")
print(scalar_param.value)  # 3.14
scalar_param.variable = "pi_val"

bool_param = Boolean(value=True, annotation="Enable feature")
print(bool_param.value)  # True

int_param = Integer(value=10, annotation="Max retries")
print(int_param.value)  # 10

text_param = Text(value="Hello", annotation="Greeting message")
print(text_param.value)  # Hello

# Serialize
serialized = scalar_param.serialize("pi")
print(serialized)
      </code></pre>
    </section>

  </div>
</div>

<div class="api-documentation" style="font-family: Arial, sans-serif; line-height:1.3; border:3px solid #2196F3; border-radius:6px; overflow:hidden; margin-top:1em;">

  <!-- Top header strip -->
  <div style="background-color:#2196F3; color:white; padding:0.5em 0.8em; font-weight:bold; font-size:1.2em;">
    ImagerData Properties
  </div>

  <!-- Content -->
  <div style="padding:0.8em;">

    <p style="margin-top:0; margin-bottom:0.5em;">
      Read-only accessor properties for the unpacked imager message data.
    </p>

    <section class="properties" style="margin-bottom:0.5em;">
      <h3 style="margin-bottom:0.2em; font-size:1em;">Properties</h3>
      <ul style="margin-top:0; margin-bottom:0.5em; padding-left:1.2em;">
        <li>
          <strong>image</strong> <em>(np.ndarray | None)</em><br>
          Return the image as a NumPy array, if available.
        </li>
        <li>
          <strong>detector_name</strong> <em>(str | None)</em><br>
          Return the detector name, if available.
        </li>
        <li>
          <strong>acquisition_name</strong> <em>(str | None)</em><br>
          Return the acquisition type, if available.
        </li>
        <li>
          <strong>stage_coordinates</strong> <em>(tuple[float, float, float] | None)</em><br>
          Return (x, y, z) stage coordinates, if available.
        </li>
      </ul>
    </section>

    <section class="usage" style="margin-top:0.5em;">
      <h3 style="margin-bottom:0.2em; font-size:1em;">Usage Example</h3>
      <pre style="margin:0; padding:0.5em; background-color:#f7f7f7; border-radius:4px;"><code class="python">
# Assuming `imager_data` is an instance of ImagerData

# Access the NumPy image
img_array = imager_data.image
print(img_array.shape if img_array is not None else "No image available")

# Access detector name
detector = imager_data.detector_name
print(detector or "No detector available")

# Access acquisition type
acq_type = imager_data.acquisition_name
print(acq_type or "No acquisition type available")

# Access stage coordinates
coords = imager_data.stage_coordinates
print(coords or "Stage coordinates not available")
      </code></pre>
    </section>

  </div>
</div>


## XYZ Stage positions

<div class="api-documentation" style="font-family: Arial, sans-serif; line-height:1.3; border:3px solid #2196F3; border-radius:6px; overflow:hidden; margin-top:1em;">

  <!-- Top header strip -->
  <div style="background-color:#2196F3; color:white; padding:0.5em 0.8em; font-weight:bold; font-size:1.2em;">
    XYStagePosition
  </div>

  <!-- Content -->
  <div style="padding:0.8em;">

    <p style="margin-top:0; margin-bottom:0.5em;">
      Represents the XYZ stage position and hardware autofocus settings.
    </p>

    <section class="attributes" style="margin-bottom:0.5em;">
      <h3 style="margin-bottom:0.2em; font-size:1em;">Constructor Parameters</h3>
      <ul style="margin-top:0; margin-bottom:0.5em; padding-left:1.2em;">
        <li><strong>name</strong> <em>(str)</em> – Name of the stage position.</li>
        <li><strong>x</strong> <em>(float)</em> – X coordinate of the stage, in <strong>microns</strong>.</li>
        <li><strong>y</strong> <em>(float)</em> – Y coordinate of the stage, in <strong>microns</strong>.</li>
        <li><strong>z</strong> <em>(float)</em> – Z coordinate of the stage, in <strong>microns</strong>.</li>
        <li><strong>usinghardwareautofocus</strong> <em>(bool, optional)</em> – Whether hardware autofocus is used. Default: <code>False</code>.</li>
        <li><strong>hardwareautofocusoffset</strong> <em>(float, optional)</em> – Offset for hardware autofocus, in <strong>microns</strong>. Default: <code>0.0</code>.</li>
      </ul>
    </section>

    <section class="usage" style="margin-top:0.5em;">
      <h3 style="margin-bottom:0.2em; font-size:1em;">Usage Example</h3>
      <pre style="margin:0; padding:0.5em; background-color:#f7f7f7; border-radius:4px;"><code class="python">
# Create a stage position (coordinates in microns)
stage_pos = XYStagePosition(
    name="Position1",
    x=12500.0,  # 12.5 mm -> 12500 microns
    y=7300.0,   # 7.3 mm -> 7300 microns
    z=0.0,
    usinghardwareautofocus=True,
    hardwareautofocusoffset=200.0  # in microns
)

# Access coordinates
print(stage_pos.x, stage_pos.y, stage_pos.z)  # microns

# Check autofocus
print(stage_pos.usinghardwareautofocus)
print(stage_pos.hardwareautofocusoffset)  # microns
      </code></pre>
    </section>

  </div>
</div>

## Output types (Decisions)

<!-- DoTimes -->
<div class="api-documentation" style="font-family: Arial, sans-serif; line-height:1.3; border:3px solid #2196F3; border-radius:6px; overflow:hidden; margin-top:1em;">
  <div style="background-color:#2196F3; color:white; padding:0.5em 0.8em; font-weight:bold; font-size:1.2em;">
    DoTimes
  </div>
  <div style="padding:0.8em;">
    <p style="margin-top:0; margin-bottom:0.5em;">Represents a “Do Times” decision with a fixed number of repeats.</p>
    <section class="attributes" style="margin-bottom:0.5em;">
      <h3 style="margin-bottom:0.2em; font-size:1em;">Constructor Parameters</h3>
      <ul style="margin-top:0; margin-bottom:0.5em; padding-left:1.2em;">
        <li><strong>ntotal</strong> <em>(int)</em> – Total number of repetitions.</li>
      </ul>
    </section>
    <section class="usage" style="margin-top:0.5em;">
      <h3 style="margin-bottom:0.2em; font-size:1em;">Usage Example</h3>
      <pre style="margin:0; padding:0.5em; background-color:#f7f7f7; border-radius:4px;"><code class="python">
decision = DoTimes(ntotal=5)
print(decision.to_decision())
      </code></pre>
    </section>
  </div>
</div>

<!-- TimeLapse -->
<div class="api-documentation" style="font-family: Arial, sans-serif; line-height:1.3; border:3px solid #2196F3; border-radius:6px; overflow:hidden; margin-top:1em;">
  <div style="background-color:#2196F3; color:white; padding:0.5em 0.8em; font-weight:bold; font-size:1.2em;">
    TimeLapse
  </div>
  <div style="padding:0.8em;">
    <p style="margin-top:0; margin-bottom:0.5em;">Represents a time-lapse decision with total steps and time intervals.</p>
    <section class="attributes" style="margin-bottom:0.5em;">
      <h3 style="margin-bottom:0.2em; font-size:1em;">Constructor Parameters</h3>
      <ul style="margin-top:0; margin-bottom:0.5em; padding-left:1.2em;">
        <li><strong>ntotal</strong> <em>(int)</em> – Total number of steps.</li>
        <li><strong>timedelta</strong> <em>(float)</em> – Time interval between steps.</li>
      </ul>
    </section>
    <section class="usage" style="margin-top:0.5em;">
      <h3 style="margin-bottom:0.2em; font-size:1em;">Usage Example</h3>
      <pre style="margin:0; padding:0.5em; background-color:#f7f7f7; border-radius:4px;"><code class="python">
timelapse = TimeLapse(ntotal=10, timedelta=5.0)
print(timelapse.to_decision())
      </code></pre>
    </section>
  </div>
</div>

<!-- RelativeStageLoop -->
<div class="api-documentation" style="font-family: Arial, sans-serif; line-height:1.3; border:3px solid #2196F3; border-radius:6px; overflow:hidden; margin-top:1em;">
  <div style="background-color:#2196F3; color:white; padding:0.5em 0.8em; font-weight:bold; font-size:1.2em;">
    RelativeStageLoop
  </div>
  <div style="padding:0.8em;">
    <p style="margin-top:0; margin-bottom:0.5em;">Represents a relative stage loop decision with optional negative/positive planes in X, Y, Z.</p>
    <section class="attributes" style="margin-bottom:0.5em;">
      <h3 style="margin-bottom:0.2em; font-size:1em;">Constructor Parameters</h3>
      <ul style="margin-top:0; margin-bottom:0.5em; padding-left:1.2em;">
        <li><strong>dx</strong> <em>(float)</em> – X movement in microns.</li>
        <li><strong>dy</strong> <em>(float)</em> – Y movement in microns.</li>
        <li><strong>dz</strong> <em>(float)</em> – Z movement in microns.</li>
        <li><strong>nNegX</strong> <em>(int)</em> – Number of additional negative planes in X.</li>
        <li><strong>nNegY</strong> <em>(int)</em> – Number of additional negative planes in Y.</li>
        <li><strong>nNegZ</strong> <em>(int)</em> – Number of additional negative planes in Z.</li>
        <li><strong>nPosX</strong> <em>(int)</em> – Number of additional positive planes in X.</li>
        <li><strong>nPosY</strong> <em>(int)</em> – Number of additional positive planes in Y.</li>
        <li><strong>nPosZ</strong> <em>(int)</em> – Number of additional positive planes in Z.</li>
        <li><strong>returntostartingposition</strong> <em>(bool)</em> – Whether to return to the starting position after the loop.</li>
      </ul>
    </section>
    <section class="usage" style="margin-top:0.5em;">
      <h3 style="margin-bottom:0.2em; font-size:1em;">Usage Example</h3>
      <pre style="margin:0; padding:0.5em; background-color:#f7f7f7; border-radius:4px;"><code class="python">
loop = RelativeStageLoop(
    dx=10.0, dy=5.0, dz=2.0,
    nNegX=1, nNegY=0, nNegZ=0,
    nPosX=1, nPosY=1, nPosZ=0,
    returntostartingposition=True
)
print(loop.to_decision())
      </code></pre>
    </section>
  </div>
</div>

<!-- StageLoop -->
<div class="api-documentation" style="font-family: Arial, sans-serif; line-height:1.3; border:3px solid #2196F3; border-radius:6px; overflow:hidden; margin-top:1em;">
  <div style="background-color:#2196F3; color:white; padding:0.5em 0.8em; font-weight:bold; font-size:1.2em;">
    StageLoop
  </div>
  <div style="padding:0.8em;">
    <p style="margin-top:0; margin-bottom:0.5em;">Represents a stage loop containing multiple XYStagePosition objects.</p>

    <section class="attributes" style="margin-bottom:0.5em;">
      <h3 style="margin-bottom:0.2em; font-size:1em;">Constructor</h3>
      <ul style="margin-top:0; margin-bottom:0.5em; padding-left:1.2em;">
        <li>No parameters. Initializes an empty list of positions.</li>
      </ul>
    </section>

    <section class="methods" style="margin-bottom:0.5em;">
      <h3 style="margin-bottom:0.2em; font-size:1em;">Methods</h3>
      <ul style="margin-top:0; margin-bottom:0.5em; padding-left:1.2em;">
        <li>
          <strong>append_stage_position(position: XYStagePosition)</strong><br>
          Add a stage position to the loop.
        </li>
        <li>
          <strong>remove_stage_position(position: XYStagePosition)</strong><br>
          Remove <em>all</em> positions with the same name as the given position.
        </li>
      </ul>
    </section>

    <section class="usage" style="margin-top:0.5em;">
      <h3 style="margin-bottom:0.2em; font-size:1em;">Usage Example</h3>
      <pre style="margin:0; padding:0.5em; background-color:#f7f7f7; border-radius:4px;"><code class="python">
stage_loop = StageLoop()

# Append positions
pos1 = XYStagePosition("Pos1", x=1000, y=2000, z=0)
pos2 = XYStagePosition("Pos2", x=1100, y=2100, z=0)
stage_loop.append_stage_position(pos1)
stage_loop.append_stage_position(pos2)

# Remove positions by name (removes all positions with same name)
stage_loop.remove_stage_position(pos1)

# Inspect decision dict
print(stage_loop.to_decision())
      </code></pre>
    </section>
  </div>
</div>