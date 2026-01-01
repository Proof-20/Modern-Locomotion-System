MLS - Modern Locomotion System
A comprehensive, modular locomotion system for Unreal Engine 5 designed for modern character movement with advanced animation features.

🚀 Features
Core Systems
Pivot System - Advanced start, stop, and directional pivots with motion matching support
Aim Offset - Smooth head/spine tracking with automatic alpha blending
Foot IK - Ground adaptation and surface normal detection
Lean System - Dynamic character leaning based on movement and rotation
Offset Root Bone - Root motion compensation for smooth transitions
Key Highlights
Motion Matching Ready - Designed to work seamlessly with UE5's motion matching
Modular Architecture - Each system is independent and can be enabled/disabled
C++ Performance - Full C++ implementation for maximum performance
Input-Driven Logic - Responsive to player input rather than just speed thresholds
Frame-Perfect Detection - Precise state transition detection
📋 System Requirements
Unreal Engine 5.0+
C++ compilation support
Motion Matching plugin (recommended)
🛠️ Installation
Copy the MLS source files to your project's Source directory
Add the following to your project's .Build.cs file:
cpp
Regenerate project files and compile
🎯 Quick Setup
1. Character Setup
cpp
2. Animation Blueprint
Inherit from USCRYFY_OBSAnimInstance
Access locomotion data via LocomotionSettings
Use the provided component outputs in your animation graph
3. Basic Configuration
cpp
🎮 System Breakdown
Pivot System
Handles character start, stop, and directional transitions:

Start Pivots - Triggered when transitioning from idle to movement
Stop Pivots - Activated when character begins stopping
Moving Pivots - Direction changes while moving
Jog Transitions - Special handling for walk→jog changes
cpp
Aim Offset System
Provides natural head and spine movement:

Camera-relative aiming with automatic alpha blending
Configurable thresholds and fade zones
Spine twist distribution
Smooth interpolation
Foot IK System
Ground adaptation and surface contact:

Automatic ground detection via line traces
Surface normal calculation
Smooth IK alpha blending
Grounded state awareness
Lean System
Dynamic character leaning during movement:

Lateral movement leaning
Rotational velocity compensation
Input-based directional leaning
State-aware multipliers
🔧 Configuration
Locomotion Core Settings
cpp
Pivot Settings
cpp
🎨 Animation Blueprint Integration
Using Pivot Data
cpp
Chooser Tables
Set up chooser tables using CurrentPivotState enum:

None → Loop animations
Start Starting → Start pivot animations
Stop Stopping → Stop pivot animations
Start Pivoting → Moving pivot animations
Aim Offset Integration
cpp
🐛 Debugging
Enable debug output in any component:

cpp
Debug information includes:

Current system states
Transition triggers
Threshold comparisons
Timer values
Speed and acceleration data
⚡ Performance Notes
All systems use cached references to avoid repeated lookups
Frame-to-frame state tracking minimizes computation
Optional debug output (disabled in shipping builds)
Modular design allows disabling unused systems
Raw velocity used for pivot detection (no smoothing overhead)
🔄 Update Order
The system updates in this order for optimal results:

UpdateLocomotionComponent - Core movement state
PivotSystemComponent - Pivot detection and management
AimOffsetComponent - Head/spine tracking
OffsetRootBoneComponent - Root motion compensation
FootIKComponent - Ground adaptation
LeanSystemComponent - Character leaning
📝 Notes
Designed for motion matching workflows
No orientation warping (handled by motion matching)
Input-driven rather than speed-driven for responsive feel
Compatible with standard UE5 character movement
Extensible architecture for custom additions
🤝 Contributing
This system is designed to be modular and extensible. Each component can be modified independently without affecting others.
