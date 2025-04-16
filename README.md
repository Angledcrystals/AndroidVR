https://vrisalotoffun.github.io/AndroidVR/

This is simple to use, simply relax your eyes to allow both images to drift together.

This tool starts from the pixel; the most basic point of light in an image. 

But instead of treating each pixel as a flat bit of color, It is treated as a living unit of perception. 

Every pixel contains two critical qualities: brightness and saturation. Brightness is used as a measure of presence or nearness, and saturation as a sense of density or form. Together, they become the raw material for a new kind of depth.

My tool reads these values across an image and creates a spatial field; not using traditional 3D geometry or camera-based depth maps.

The result is a depth matrix.

Here are the suggested values for creating depth in AndroidVR.

![image](https://github.com/user-attachments/assets/36f2015b-7e4e-4a9b-877f-6fbeddc04435)

**How does this tool use a Square Wave?**

The essential part of the quantization is in this line:
JavaScript

const quantizedDepth = Math.floor(depth / stepSize) * stepSize;

This creates a stair-step function which is mathematically equivalent to a square wave transform:

    The continuous depth values (0-255) are divided into discrete bands
    Within each band, all values are flattened to a single value
    This creates sharp, vertical transitions between depth levels


![image](https://github.com/user-attachments/assets/9b5675dc-7813-4c91-adb1-7dcd89856638)


This matches the definition of a square wave transform because:

    It has binary-like transitions between states
    The transitions are immediate (vertical) rather than gradual
    The output signal consists of flat plateaus at discrete levels

When you adjust the "Levels" slider, you're controlling the number of steps in this square wave pattern - fewer levels means more pronounced steps with greater contrast between depth planes.

**Notice**

Be VERY careful about using 3D flicker mode, this mode is intended for people who have mono vision and should not be used by those who have binocular vision due to the cognitive strain it puts on the user when input is received through both eyes.

**Transfer to Natural Vision**

**Temporary effects**: 10-30 minutes of aftereffects might occur immediately after 1-2 hour sessions

**Initial transfer**: Minor involuntary interpretation might begin after 15-20 hours of cumulative exposure (across multiple days)

**Measurable adaptation**: 30-50 hours of training over 3-6 weeks would be needed for your brain to begin consistently applying these cues in natural environments

**Robust integration**: 100+ hours over 2-4 months for substantial, persistent effects when not using the app

VRwizard is a 2D system designed to simulate a 3D depth perception experience using visual cues such as luminosity and saturation. It allows users to experience depth without the traditional complexities and risks associated with fully immersive 3D virtual reality, maintaining alignment with real-world sensory input to ensure user safety and comfort.

---

### Key Functions:

1. **Depth Perception Simulation**
   - **Function**: Simulates depth through manipulation of visual cues (luminosity, saturation).
   - **Purpose**: Trains the brain to interpret depth in a 2D system, enhancing spatial awareness and visual processing.

2. **Visual Alignment with Real-World Input**
   - **Function**: Aligns the virtual depth cues with real-world sensory feedback (e.g., movement, position).
   - **Purpose**: Ensures users stay grounded in their physical environment, reducing the risk of disorientation and confusion.

3. **User Interaction with Virtual Depth**
   - **Function**: Allows users to interact with the depth simulation by adjusting tilt or other input methods.
   - **Purpose**: Engages the user in actively processing depth, reinforcing neural pathways for visual-motor coordination and spatial navigation.

4. **Safe Virtual Experience Design**
   - **Function**: Minimizes cognitive load and overstimulation by offering a controlled, non-immersive environment.
   - **Purpose**: Provides a safer alternative to traditional VR experiences by reducing the risk of sensory overload and mental fatigue.

5. **Grounded User Experience**
   - **Function**: Keeps the user's experience aligned with their physical reality, preventing confusion between the virtual and real worlds.
   - **Purpose**: Ensures that users maintain a clear sense of spatial orientation, preventing any loss of connection with the real world.

6. **Neurological Training**
   - **Function**: Stimulates neuroplasticity by encouraging the brain to adapt to new visual depth cues and spatial relationships.
   - **Purpose**: Enhances cognitive functions related to visual processing, spatial awareness, and motor coordination.

7. **Mindfulness and Cognitive Clarity**
   - **Function**: Promotes focus and attention through the grounded, low-stress nature of the tool.
   - **Purpose**: Helps users stay mentally present, encouraging mindfulness and reducing mental clutter or distractions.

### Purpose & Objective:
- **VRwizard** is designed to condition users’ brains to process visual depth more effectively, using a non-traditional method that minimizes cognitive strain. The system serves as a safe environment for improving spatial awareness, visual processing, and overall cognitive function while staying grounded in real-world input to prevent any perceptual confusion or disorientation.

### Key Benefits:
- Improved depth perception and spatial awareness.
- Enhanced cognitive processing, focus, and mental clarity.
- Safe exploration of virtual depth with minimal risk of overstimulation or confusion.
- Low-risk, controlled environment for cognitive and perceptual development.

### Safety Features:
- Aligned with real-world sensory input to maintain spatial awareness.
- Minimal cognitive load to reduce the risk of mental fatigue and overstimulation.
- User safety features designed to prevent disorientation, motion sickness, and confusion.
