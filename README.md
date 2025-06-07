https://Angledcrystals.github.io/AndroidVR/

Rewritten by AI for readability.

# Invisible Mirror

**Invisible Mirror** is a real-time camera web app that transforms live video into dynamic depth and stereo visualizations using advanced Mirror geometry. It combines mathematics, band detection, and interactive controls to create immersive, information-rich visual effects ideal for stereo viewing, VR, and computational photography.

Invisible Mirror is computationally expensive, only the very best hardware for phones can run it in this era; this is a case of the HW not being able to run the code efficiently...

To give an idea of the requirements, it will run on iPhone SE3 at 25 FPS on high quality, lol.

Invisible Mirror does not have as many fun features as VRWizard, and it is not suitable for training perception; it is just theory put into practice.

Also I use esoteric terminology for the functions because I think it is funny.

Here is a example of how good the depth map created is, when applied to a 2D image that didn't normally have one.

As we can see, Hband does indeed recover 3D data from 2D.

![topimage-classic-hamburger-2019m04-800x534-600x401](https://github.com/user-attachments/assets/f9021dd6-d872-4db7-a4ff-d3376bbef16a)

![topimage-classic-hamburger-2019m04-800x534-600x401](https://github.com/user-attachments/assets/a41bb8b5-bd20-453c-ac89-efeffd556050)


## ✨ Features

- **Live Mirror Geometry**  
  Transform the live camera feed using precise θ (theta) and φ (phi) angle controls, supporting 0.1° increments for fine manipulation.

- **Advanced Band Detection**  
  Multiple detection modes (Auto, Content, Gradient, Statistical, Manual, Full Image) identify and amplify information-rich visual "bands" in real time.

- **Depth Map Generation**  
  Computes a continuous depth map from the camera using Mirror mathematics, with options for luminance, saturation, and band focus.

- **Depth Contrast Control**  
  Easily adjust depth contrast to customize the stereo effect and highlight subtle or bold depth cues.

- **Stereo 3D Output**  
  Generates left/right images with pixel offsets based on the computed depth, ready for parallel stereo viewing (with optional cross-eye mode).

- **Live Controls & Presets**  
  All parameters—Mirror angles, band size, focus, luminance/saturation weighting, stereo separation, depth intensity, and more—are adjustable in real time. Presets for quick experimentation.

- **Performance Optimized**  
  Runs efficiently in modern browsers with adjustable quality for smooth operation on both desktop and mobile.

- **Debugging and Analysis Tools**  
  Includes live FPS, processing stats, and a raw camera feed for troubleshooting and calibration.

## 🧮 Technology

- **Spherical → Cartesian Projection**
- **Householder Reflection for band direction**
- **Stereographic Mapping**
- **Band-focused, content-aware depth computation**
- **Real-time JavaScript, WebRTC, and Canvas rendering**

## 🚀 Use Cases

- Stereo photography and VR/AR visualization
- Computational imaging and artistic effects
- Mathematical demonstrations and education
- Accessibility: Enhanced depth perception for vision assistance

## 🛠️ Getting Started

1. Clone or download the repo.
2. Open the main HTML file in a modern browser (Chrome/Edge/Firefox, mobile or desktop).
3. Grant camera permissions when prompted.
4. Adjust parameters and explore the live Mirror transformation!

## 📖 License

Invisible Mirror is licensed under the GNU General Public License v3.0 (GPLv3).  
This ensures that all modified versions and redistributions remain free and open.

## Q&A

**How does Invisible Mirror work?**

Invisible Mirror uses a mathematical transformation called the Hadit transform to analyze every pixel of your camera image in spherical coordinates (θ, φ). It projects these directions onto a "Hadit band" using advanced geometry, then computes a depth value for each pixel based on how it relates to this band and the content (luminance, saturation, etc).
The Core Steps:

    Spherical Mapping:
        Each pixel's location is mapped to a direction on the unit sphere using θ (azimuth) and φ (inclination).
    Hadit Vector Reflection:
        A user-chosen direction (the "Hadit vector", set by θ/φ controls) is used to define an "information band" on the sphere.
        The algorithm reflects each pixel's direction across the Hadit vector using a mathematical operation called a Householder reflection.
    Stereographic Projection (S-Coordinate):
        The reflected direction is mapped to a 2D plane using stereographic projection.
        The result is a 2D vector called the S-coordinate (S.x, S.y) for each pixel.
    Band Detection & Depth:
        The magnitude of the S-coordinate (distance from the center in the projected plane) is used to detect bands of "interesting" information.
        Pixels whose S-magnitude falls within this band are considered "in focus" or "important".
        The final depth of each pixel is computed based on how it relates to this band, optionally modulated by luminance and saturation.

**What is the S-coordinate?**

    The S-coordinate is a 2D vector resulting from the stereographic projection of a reflected spherical direction (after the Householder reflection).
    It essentially tells you how far and in what direction a pixel lies from the "Hadit vector" (the focus direction) when mapped from the sphere onto a plane.
    S-magnitude (the length of S) is used to group pixels into "bands" (rings or stripes) relative to the Hadit direction.
    
    The S-coordinate is a mathematical way to measure "distance from the focus direction" after mapping the 3D sphere onto a 2D plane.
    It's the core of how Invisible Mirror finds and enhances "bands" of visual information in your camera feed.

## How the H-Band Creates Functional Depth
How the H-Band Creates Functional Depth Maps Through Pure Geometry

The H-Band (Hadit Band) generates depth maps using pure mathematical geometry without needing brightness or saturation. Here's how:

// 1. PIXEL POSITION → SPHERICAL COORDINATES
const gTheta = (px / width) * 360;        // X position → longitude
const gPhi = (py / height) * 180;         // Y position → latitude
const G_3d = sphericalToCartesian(gTheta, gPhi);

// 2. HOUSEHOLDER REFLECTION (pure geometry)
const hadit_3d = sphericalToCartesian(config.haditTheta, config.haditPhi);
const G_reflected = householderReflection(G_3d, hadit_3d);

// 3. STEREOGRAPHIC PROJECTION → DEPTH
const S_hadit = stereographicProjection(G_reflected);
const sMagnitude = Math.sqrt(S_hadit.x² + S_hadit.y²);

Why This Works Without Color Information:

1. Spatial Encoding

    Each pixel's (x,y) position becomes its unique geometric identifier
    No two pixels have the same spherical coordinates
    Position alone carries sufficient information for depth calculation

2. Mathematical Transformation

The Householder reflection creates systematic geometric relationships:

    Objects at similar positions undergo similar transformations
    The reflection preserves spatial relationships mathematically
    Geometric consistency emerges from pure mathematics

3. S-Magnitude as Depth

// S-magnitude directly becomes depth without color input
const depth = 0.2 + (normalizedSMagnitude * 0.8);
depth = 0.5 + (depth - 0.5) * config.focusFactor;

4. The 0.1° Effect

With 0.1° precision, the H-Band becomes linear, meaning:

    The entire image falls within one coherent geometric transformation
    All pixels receive mathematically consistent depth treatment
    No need for content-based segmentation

Functional Depth Without Color Because:

    Position = Identity: Each pixel's location is its unique geometric signature
    Mathematical Coherence: The transformation preserves spatial relationships
    Systematic Mapping: S-magnitude provides consistent depth values
    Geometric Continuity: Neighboring pixels get related depth values

What You Get:

    Spatially coherent depth based on geometric position
    Smooth depth gradients from mathematical continuity
    Predictable depth relationships from systematic transformation
    Full-image coverage due to the flattened H-Band

The H-Band essentially treats the image as a geometric surface and applies consistent mathematical depth mapping based purely on spatial coordinates - no visual content analysis required!

**The H-band is located inside the S-coordinates though, right?**

That's right, by converting the image coordinate to S-space which the S-coordinates generate, I then convert it to a sphere (the H-band) and zone in on the part of the infinite sphere, which contains all possibility..

The part I focus on is the part that contains 'proper decoding instructions' for 2D objects, then I expand that to hit the entire image creating a superior depth map.

**Licensing**

Invisible Mirror is licensed under the GNU General Public License v3.0 (GPLv3).
This ensures that all modified versions and redistributions remain free and open.
---


** Under the branch: Release Candidate **

# VR/3D Camera App Comparison Chart

VRWizard is intended to run on bad hardware, it uses a scaled-down version of S-coordinates...

Below is a technical comparison chart of AndroidVR Virtual Spectrum and several popular VR, stereo, and 3D camera applications.  
Each feature is rated, and a summary evaluation is provided at the end.

| Feature / App                                | **AndroidVR Virtual Spectrum** | **Google Cardboard Camera** | **Depthy**        | **WebXR Viewer**  | **Stereogram Apps**   | **LucidCam/Vuze/Insta360** |
|----------------------------------------------|:------------------------------:|:---------------------------:|:-----------------:|:-----------------:|:---------------------:|:--------------------------:|
| **Platform**                                | Web (no install)               | Android/iOS app             | Web               | Web/iOS           | Web/Mobile            | Hardware + Apps            |
| **Live Camera Video**                       | ✅ Yes                         | ❌ No (photos only)          | ❌ No             | ✅ Yes (AR only)   | ⚠️ Sometimes           | ✅ Yes                      |
| **Stereo Output (Side-by-Side Video)**      | ✅ Yes (live, flicker, custom) | ✅ Yes (photos)              | ❌ No             | ❌ No              | ✅ Yes (photos/GIFs)   | ✅ Yes                      |
| **Real-Time Depth Processing**              | ✅ Yes (multi-algo, tunable)   | ❌ No                        | ❌ No (photo only)| ❌ No              | ❌ No                  | ❌ No (hardware only)       |
| **User Controls/Customization**             | ⭐⭐⭐⭐⭐ Extensive                | ⭐ Minimal                   | ⭐⭐ Some          | ⭐ Minimal         | ⭐⭐ Some               | ⭐⭐ Standard                 |
| **Video Recording/Export**                  | ✅ Yes (video)                 | ❌ No                        | ✅ GIF/photo      | ❌ No              | ⚠️ Sometimes           | ✅ Yes                      |
| **Mobile Optimization**                     | ✅ Yes                         | ✅ Yes                       | ✅ Yes            | ✅ Yes             | ✅ Yes                 | ✅ Yes                      |
| **Open Source**                             | ✅ Yes                         | ❌ No                        | ✅ Yes            | ✅ Yes             | ⚠️ Mixed               | ❌ No                       |
| **Unique Depth Algorithms**                 | ✅ Yes (S-coords, vector, etc) | ❌ No                        | ⚠️ Single         | ❌ No              | ❌ No                  | ❌ No                       |
| **Flicker 3D Mode**                         | ✅ Yes                         | ❌ No                        | ❌ No             | ❌ No              | ❌ No                  | ❌ No                       |
| **Dedicated VR Hardware Support**           | ⚠️ Browser VR viewers          | ❌ No                        | ❌ No             | ⚠️ Yes (WebXR)     | ❌ No                  | ✅ Yes                      |
| **Photo-Only 3D (not video)**               | ⚠️ Optional                    | ✅ Yes                       | ✅ Yes            | ❌ No              | ✅ Yes                 | ✅ Yes                      |
| **Requires Installation**                   | ❌ No                          | ✅ Yes                       | ❌ No             | ✅ Yes (iOS app)   | ⚠️ Sometimes           | ✅ Yes                      |

**Legend:**  
✅ = Full support | ⚠️ = Partial/Optional | ❌ = Not supported | ⭐ = Customization level

---

## Evaluation: Which Wins?

- **Best for Real-Time, Custom Stereo/Depth Effects:**  
  **AndroidVR Virtual Spectrum** wins decisively if you want live camera video, advanced depth algorithms, and deep real-time customization—all in a browser, on any device, no install needed.

- **Best for Quick 3D Photos (No Live Video):**  
  **Google Cardboard Camera** and **Stereogram Apps** are better for casual users wanting quick 3D photos, but lack live video and advanced controls.

- **Best for High-Fidelity Stereo Video:**  
  **LucidCam/Vuze/Insta360** (dedicated hardware) produce the highest quality 3D video/photos, but they require buying extra hardware and using proprietary apps.

- **Best for WebXR/AR Content (Not Camera Stereo):**  
  **WebXR Viewer** is ideal if your focus is AR/VR scene rendering, not live camera-based effects.

- **Best for Post-Processing 3D Photos:**  
  **Depthy** is great for turning single photos with depth data into interactive 3D visuals or wigglegrams, but not for live video.

---

### **Overall Winner for Experimental, Customizable, Real-Time VR/3D Camera Effects:**
## 🏆 **AndroidVR Virtual Spectrum**

- **Why?** Only AndroidVR Virtual Spectrum offers live, in-browser, stereo/depth video with extensive, tunable algorithms and controls—no install, open source, and highly adaptable for experimentation, learning, and creative VR/AR workflows.

---

AndroidVR (VRwizard) is licensed under the GNU General Public License v3.0 (GPLv3).  
This ensures that all modified versions and redistributions remain free and open.
