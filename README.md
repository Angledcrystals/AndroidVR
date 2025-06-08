https://Angledcrystals.github.io/AndroidVR/

Rewritten by AI for readability.

# Invisible Mirror

Invisible Mirror is my pet project, I'll be rebuilding a LOT as I determine the correct parameters to do a extraction from S-coords...

Hband is good, for imposing S-coords on brightness based depth maps but I want to try to do it purely with S-coords

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
