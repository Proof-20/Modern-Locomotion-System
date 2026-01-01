# MLS - Modern Locomotion System

A comprehensive, modular locomotion system for Unreal Engine 5 designed for modern character movement with advanced animation features.


## 🚀 Features

### Core System

- **Pivot System** - Advanced start, stop, and directional pivots with motion matching support
- **Aim Offset** - Smooth head/spine tracking with automatic alpha blending.
- **Foot IK** - Ground adaptation and surface normal detection.
- **Lean System** - Dynamic character leaning based on movement and rotation.
- **Offset Root Bone** - Root motion compensation for smooth transitions.

### Key Highlights

- **Motion Matching Ready** - Designed to work seamlessly with UE5's motion matching
- **Modular Architecture** -  Each system is independent and can be enabled/disabled.
- **C++ Performance** - Full C++ implementation for maximum performance.
- **Input-Driven Logic** - Responsive to player input rather than just speed thresholds
- **Frame-Perfect Detection** - Precise state transition detection.

## 📋 System Requirements

- **Unreal Engine 5.0+**
- **C++ compilation support**
- **Motion Matching plugin** 

## 🛠️ Installation

Copy the MLS source files to your project's Source directory and add the following to your project's .Build.cs file:

```
PublicDependencyModuleNames.AddRange(new string[] { 
    "Core", 
    "CoreUObject", 
    "Engine",
    "AnimGraphRuntime"
});
```
Regenerate project files and compile.

## 🎯 Quick Setup (optional)

### Character Setup
```
// In your character class
UPROPERTY(VisibleAnywhere, BlueprintReadOnly, Category = "Animation")
class USCRYFY_OBSAnimInstance* AnimInstance;
```

### Animation Blueprint

- **Inherit from USCRYFY_OBSAnimInstance**
- **Access locomotion data via LocomotionSettings**
- **Use the provided component outputs in your animation graph** 

###  Basic Configuration

```
// Default thresholds (adjustable in editor)
MovementThreshold = 10.0f;
WalkSpeedThreshold = 150.0f;
JogSpeedThreshold = 300.0f;

// Pivot settings
StartSpeedThreshold = 5.0f;
StopSpeedThreshold = 80.0f;
PivotAngleThreshold = 90.0f;
PivotDuration = 0.4f;
```

## 🎮 System Breakdown

### Pivot System

Handles character start, stop, and directional transitions:
