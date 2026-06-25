# Mechanical System Design | 机械系统设计

## 1. Main Load-Bearing Frame

| Item | Spec |
|:---|:---|
| **Frame Material** | 7075-T6 Aerospace Aluminum Profile/Plate |
| **Yield Strength** | >=505 MPa |
| **Max Deformation (Full Load)** | <=0.1 mm |
| **Safety Factor** | >=4.0 |
| **Hinge/Pin Material** | 40Cr Quenched Steel, Shear >=600 MPa |

### Load Transfer Path

Upper Limb Load -> Shoulder Frame -> Torso Main Frame -> Hip Structure -> Leg Joints -> Foot Contact Surface

Full rigid closed-loop, zero load to human body.

### Docking Interface

- Quick-release docking frame on back and bottom
- Stainless steel quick-release pin lock
- 10-second rapid assembly/disassembly with power cart
- Lock force >=10x cart weight

## 2. Joint System

### 2.1 Lower Limb Joints (12 DOF)

| Joint | DOF | Per Side | Range | Notes |
|:---|:---|:---|:---|:---|
| **Hip** | 3 | x2 = 6 | Flex/Ext +/-60deg, Abd/Add, Rotation | Peak force <=3700 N |
| **Knee** | 1 | x2 = 2 | Forward flexion max 90deg | Peak dynamic torque 1471.5 Nm, core load-bearing |
| **Ankle** | 2 | x2 = 4 | Dorsiflex/Plantarflex +/-45deg, Invert/Evert +/-45deg | Slope angle real-time compensation |

### 2.2 Upper Limb Joints (6 DOF)

- Per side: **3-DOF articulated arm**
- Single arm max load: 300 kg
- Applications: Heavy lifting, carrying, demolition
- Each joint: bidirectional balance valve + pop-type anti-burst valve
- Auto-lock on power loss, instant lock on hose burst

## 3. Human-Machine Interface

| Interface | Function | Feature |
|:---|:---|:---|
| **Hip Seat** | Support seated body weight | No lateral force transfer, long-duration comfort |
| **Foot Platform** | Rigid connection to exoskeleton foot | Passive leg following, sole always parallel |
| **3-Point Quick-Release Belt** | Body restraint | No rigid lock, 1-second release, pelvic movement OK |

## 4. Height Adaptation

- Covers 160 / 175 / 190 cm height profiles
- One-click switch, adaptation time <=200 ms
- Auto-adjust seat height, foot platform position, joint zero positions