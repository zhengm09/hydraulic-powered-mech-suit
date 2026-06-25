# BOM List & Component Selection | BOM清单与选型手册

> Phase 0 - Preliminary selection. Specific models to be confirmed after Phase 1 validation.

## 1. Hydraulic Cylinders (National Standard Off-the-Shelf)

| Category | Bore/Rod | Covered Joints | Qty |
|:---|:---|:---|:---|
| **Main Load-Bearing** | 50/36 Constant-Speed Bidirectional | Hip/Knee main load, upper limb heavy lift | 8 |
| **Auxiliary** | 32/18 Bidirectional | Hip/shoulder rotation/lateral swing | 6 |
| **Fine Adjustment** | 25/14 Bidirectional | Ankle joints | 4 |
| **Total** | -- | All 18 DOF covered | **18** |

Selection Principle: All national standard off-the-shelf bidirectional cylinders, stroke utilization <=90%, 10% safety margin.

## 2. Hydraulic Valves

| Category | Spec | Location | Qty |
|:---|:---|:---|:---|
| **Proportional Valve (Lower)** | 03 port closed-loop, LVDT feedback, step <=20 ms | Lower body valve block | 12 |
| **Proportional Valve (Upper)** | 06 port closed-loop, LVDT feedback | Upper body valve block | 6 |
| **Bidirectional Overload Relief** | -- | Per joint | 18 |
| **Bidirectional Balance Valve** | -- | Per joint | 18 |
| **Pop-Type Anti-Burst Valve** | -- | Upper limb per joint | 6 |

## 3. Hydraulic Power Components

| Component | Spec | Qty |
|:---|:---|:---|
| **High-Pressure Gear Pump** | 5 mL/r, low pulsation | 2 (dual independent) |
| **Accumulator (Lower)** | 0.6 L diaphragm type | 1 |
| **Accumulator (Upper)** | 1.6 L diaphragm type | 1 |
| **Relief Valve** | Rated 16 MPa, Peak 21 MPa | 2 (one per circuit) |
| **Filter** | -- | 2 |

## 4. Sensors

| Type | Model | Location | Qty |
|:---|:---|:---|:---|
| **Absolute Encoder** | AS5600 | Each of 18 joints | 18 |
| **6-Axis IMU** | BMI088 (Industrial Grade) | Torso main frame | 1 |
| **Array Pressure Sensor** | Thin-film type | Both soles | 2 |
| **Pressure Sensor** | -- | Key nodes of dual hydraulic circuits | 4 |
| **Wrist Force Sensor** | Thin-film type | Upper limb wrist end | 2 |

## 5. Electronic Control Hardware

| Component | Model | Function |
|:---|:---|:---|
| **Main Controller** | STM32F407 Core Board | Joint scheduling, mode logic, gait planning |
| **Coprocessor** | STM32F103 Minimal System | ZMP bipedal balance (hard real-time) |
| **PWM Driver Board** | Opto-isolated 8-channel x2 | Independent proportional valve drive |

## 6. Structural Materials

| Material | Spec | Use |
|:---|:---|:---|
| **7075-T6 Aluminum Alloy** | Profile/Plate | Main load-bearing frame |
| **40Cr Quenched Steel** | Pins/Hinges | High-strength connection parts |
| **Stainless Steel** | Quick-release pins | Docking lock |

## 7. Hoses and Tubing

| Type | Spec | Use |
|:---|:---|:---|
| **High-Pressure Armored Hose** | <=5 m, Rated 25 MPa, 6/10 mm port | Pump to valve block (power transmission) |
| **Non-Armored High-Pressure Oil Tube** | -- | Valve to cylinder (joint connection) |