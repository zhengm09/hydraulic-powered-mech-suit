# Control System Design | 控制系统设计

## 1. Hardware Architecture

### 1.1 Core Boards

| Role | Model | Responsibilities |
|:---|:---|:---|
| **Main Controller** | STM32F407 Core Board | Joint scheduling, mode logic, gait planning, HMI |
| **Coprocessor** | STM32F103 Minimal System | ZMP bipedal balance calculation (hard real-time) |

### 1.2 Drive Unit
- Opto-isolated 8-channel hardware PWM driver board x2
- Single-channel independent drive for proportional valve
- No bus delay, sufficient safety redundancy

### 1.3 Power Supply Scheme
- Powered by power cart 48V DC bus
- Step-down to separate circuits: control, sensor, solenoid valve

## 2. Core Control Logic

### 2.1 Dual-Closed-Loop Control

Each joint uses double closed-loop:
- **Inner loop**: Valve spool position closed-loop - ensures valve response linearity
- **Outer loop**: Joint angle closed-loop - high-precision position control

### 2.2 Bipedal Balance Control (ZMP)
- Based on Zero Moment Point control theory
- Sole array pressure sensor real-time collection of center of gravity position
- Hip, knee, ankle coordinated adjustment to maintain center of gravity within support polygon
- Slope walking: ankle joint real-time angle compensation, response <=100 ms

### 2.3 Time-Division Work Interlock
- **Hardware level**: Independent hardware interlock circuit - upper body action forces lower body lock, and vice versa
- **Software level**: Pre-check upper/lower body status before all action triggers and mode switches

### 2.4 Three-Height Auto-Adaptation
- Built-in 160 / 175 / 190 cm reference parameter library
- One-click switch, adaptation time <=200 ms
- Auto-adjust seat height, foot platform position, joint zero positions

## 3. Sensor Configuration

| Sensor | Model | Location | Function |
|:---|:---|:---|:---|
| **Absolute Encoder** | AS5600 | Each of 18 joints (x1) | Angle collection, closed-loop feedback, range +/-180 deg no blind spot |
| **6-Axis IMU** | BMI088 (Industrial Grade) | Torso main frame | Tilt angle collection, accuracy <=+/-0.2 deg |
| **Array Pressure Sensor** | Thin-film type | Both soles | ZMP real-time collection, center of gravity monitoring |
| **Pressure Sensor** | -- | Key nodes of dual hydraulic circuits | System pressure monitoring, overload protection trigger |
| **Wrist Force Sensor** | Thin-film type | Upper limb wrist end | Admittance control force data collection |

## 4. Control Priority

| Circuit | Frequency | Notes |
|:---|:---|:---|
| **Lower Body Joints** | 1 kHz | Bipedal balance precise control |
| **Upper Body Joints** | 100 Hz | Heavy lifting, lower precision requirement |