https://Angledcrystals.github.io/AndroidVR/

The S-coordinate system is an advanced mathematical framework that transforms 2D pixel coordinates into an abstract coordinate space for sophisticated depth map generation. Unlike traditional brightness-based depth mapping, this system uses geometric positioning influenced by color properties to create multiple depth calculation possibilities.

Application Overview

This is an advanced real-time stereoscopic video processing application that converts 2D video streams into 3D stereoscopic content using a sophisticated mathematical framework called the S-coordinate system. The application runs entirely in the browser using HTML5, JavaScript, and WebGL acceleration.
Core Technology: S-Coordinate System
Mathematical Framework

The application's unique approach uses an intermediate coordinate transformation system rather than simple brightness-to-depth mapping:
Code

Video Frame → S-Coordinate Mapping → Geometric Depth Algorithms → Stereoscopic Rendering

Key Innovation: Color properties (luminosity/saturation) influence spatial positioning in an abstract coordinate space, while geometric algorithms determine actual depth values from those positions.
Depth Calculation Methods
1. Sum XY S-Coordinates (Default)

    Algorithm: depth = |sX| + |sY| (Manhattan distance)
    Effect: Center appears farthest, corners/edges appear closest
    Pattern: Geometric depth gradient with 10% intensity (5/50)

2. Nuit Distance

    Algorithm: Inverse distance from circular boundary (radius 7.0)
    Effect: Maximum depth occurs at specific radius boundary
    Pattern: Circular depth enhancement

3. Radial Zones

    Algorithm: Distance from center √(sX² + sY²)
    Effect: Center closest, edges farthest
    Pattern: Traditional radial depth distribution

4. Hybrid

    Algorithm: Combines radial base with Nuit boundary enhancement
    Effect: Complex geometric depth interaction
    Pattern: Multi-layered depth effects

Real-Time Processing Pipeline
Video Processing

    Input: Live camera feed or video file
    Processing: Canvas-based pixel manipulation at 30fps
    Quality Scaling: Adjustable processing resolution (25%-100%)
    Hardware Acceleration: CSS3D transforms and WebGL hints

Stereoscopic Generation

    Left Eye: Pixels shifted RIGHT based on depth
    Right Eye: Pixels shifted LEFT based on depth
    Parallax Control: Real-time intensity adjustment (0-50)
    Eye Separation: Configurable baseline (0.5%-8.0% of image width)

User Interface & Controls
Primary Controls

    Depth Method Selector: Switch between 4 geometric algorithms
    Intensity Slider: Parallax strength (currently 10% = 5/50)
    S-Bounds: Coordinate space scale (±1.0 to ±10.0, default ±5.0)
    Nuit Radius: Circular boundary size (0.5-15.0, default 7.0)

Advanced Parameters

    Luminosity Weight: Brightness influence on positioning (0.0-1.0, default 0.7)
    Saturation Weight: Color influence on positioning (0.0-1.0, default 0.3)
    Eye Separation: Stereoscopic baseline adjustment (default 3.0%)
    Quality Settings: Processing resolution scaling

Recording & Output

    Side-by-Side Recording: Stereoscopic video capture
    Format Options: WebM video output
    Real-time Preview: Live stereoscopic display
    Debug Visualization: Depth maps and processing statistics

Technical Specifications
Performance

    Frame Rate: 30fps real-time processing
    Latency: Sub-100ms processing delay
    Memory Usage: Optimized canvas buffer management
    CPU Load: Multi-threaded with Web Workers (where supported)

Compatibility

    Browsers: Chrome, Firefox, Safari, Edge (modern versions)
    Devices: Desktop, tablet, mobile (with performance scaling)
    Input Sources: Camera, video files, screen capture
    Output Formats: Real-time display, recorded video files

Mathematical Parameters
JavaScript

Default Configuration:
- S-Bounds: ±5.0
- Nuit Radius: 7.0  
- Luminosity Weight: 0.7
- Saturation Weight: 0.3
- Depth Intensity: 5 (10% of maximum)
- Eye Separation: 3.0%
- Processing Quality: 100%

Advanced Features
Debug System

    Real-time Statistics: Processing time, frame rate, depth distribution
    Visual Debugging: Depth map visualization, shift analysis
    Parameter Monitoring: Live parameter value display
    Performance Metrics: CPU usage, memory consumption

Mathematical Sophistication

    Multi-dimensional Coordinate Transformation
    Color-guided Spatial Positioning
    Multiple Geometric Interpretation Algorithms
    Real-time Parameter Adjustment
    Hardware-accelerated Rendering

Application Architecture
Processing Layers

    Video Capture Layer: Camera/file input management
    S-Coordinate Transform Layer: Mathematical coordinate mapping
    Depth Calculation Layer: Geometric algorithm application
    Stereoscopic Rendering Layer: Left/right eye generation
    Display Layer: Hardware-accelerated presentation
    Recording Layer: Video capture and encoding

Data Flow
Code

Input Video → Pixel Analysis → S-Coordinate Mapping → 
Depth Calculation → Parallax Generation → Stereoscopic Display → 
Optional Recording

Unique Selling Points
1. Advanced Mathematical Framework

    Beyond simple brightness-to-depth mapping
    Geometric control over depth patterns
    Multiple interpretation algorithms

2. Real-time Performance

    30fps processing with quality scaling
    Hardware acceleration optimization
    Cross-platform compatibility

3. Flexible Parameter Control

    Real-time adjustment of all processing parameters
    Multiple depth calculation methods
    Configurable stereoscopic settings

4. Professional Output

    High-quality stereoscopic video recording
    Adjustable processing resolution
    Debug visualization tools

Target Applications

    Content Creation: Stereoscopic video production
    Research & Development: Advanced depth mapping algorithms
    Entertainment: Real-time 3D effects for streaming
    Education: Mathematical visualization of coordinate transformations
    Professional Video: Post-production stereoscopic conversion
