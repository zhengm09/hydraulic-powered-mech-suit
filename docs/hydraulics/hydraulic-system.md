# Hydraulic System Design | 液压系统设计

## 1. Dual Independent Circuit Architecture

### 1.1 Lower Body Subsystem (Pump #1)
- Covers lower limb **12 joints**
- Rated pressure: 16 MPa
- High-frequency precise control for bipedal balance and heavy-load pressure holding
- 03-port high-response closed-loop proportional valve (LVDT feedback, step <=20 ms)
- 0.6 L diaphragm accumulator

### 1.2 Upper Body Subsystem (Pump #2)
- Covers upper limb **6 joints**
- Rated pressure: 16 MPa
- Large flow for heavy lifting requirements
- 06-port closed-loop proportional directional valve (LVDT feedback)
- 1.6 L diaphragm accumulator

### 1.3 Isolation Guarantee
- **No merging, no cross-talk** - two systems physically completely isolated
- Each has independent relief valve, filter, accumulator
- Faults do not affect each other

## 2. Integrated Valve Block Design

### 2.1 Installation Constraints
- Width <=220 mm, Height <=100 mm, Depth <=200 mm
- Fits narrow installation space in exoskeleton frame
- Installed close to corresponding joint group

### 2.2 Valve Configuration (Per Joint)
- **Bidirectional integrated overload relief valve** - impact buffering during stance phase
- **Bidirectional balance valve** - power-off pressure holding
- **Pop-type anti-burst valve** (upper limb only) - instant lock on hose burst

## 3. Accumulator and Hose Design

### 3.1 Accumulator Configuration

| Location | Spec | Function |
|:---|:---|:---|
| Near lower body valve block | 0.6 L diaphragm type | Compensate lower limb peak flow, offset hose pressure loss |
| Near upper body valve block | 1.6 L diaphragm type | Compensate upper limb lifting large flow demand |

### 3.2 Hose Specifications

| Section | Type | Pressure Rating | Port Size | Performance |
|:---|:---|:---|:---|:---|
| Pump to Valve Block | <=5 m high-pressure armored hose | 25 MPa | 6/10 mm | Loss <=0.3 MPa, Delay <=30 ms |
| Valve to Cylinder | Non-armored high-pressure oil tube | -- | -- | Accommodates joint bending, sufficient margin |

## 4. Hydraulic Cylinder Selection Principles

- All national standard off-the-shelf bidirectional cylinders, no custom parts
- Stroke utilization <=90%, 10% safety margin reserved
- No over-travel or dead point at maximum angle in all scenarios