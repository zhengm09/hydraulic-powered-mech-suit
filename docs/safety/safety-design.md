# Safety Design | 安全设计

## 1. Basic Safety

| Safety Measure | Implementation | Notes |
|:---|:---|:---|
| **Full-Chain Pressure Protection** | Dual system independent relief valves + real-time pressure sensors | Each circuit has independent overpressure protection |
| **Multi-Point Emergency Stop** | Hardware E-stop buttons xN | One-click cut all power output |
| **Over-Travel Limit** | Mechanical hard limit + Software soft limit | Dual joint angle protection |
| **Strong/Weak Power Isolation** | Opto-isolated PWM driver board | Physical isolation between control and power circuits |
| **Independent Hardware Safety Circuit** | Safety circuit independent of main controller | Can still execute safety actions when main controller fails |

## 2. Specialized Safety

### 2.1 Torso Tilt Over-Limit Protection
- BMI088 IMU real-time monitoring of torso tilt angle
- Exceeds threshold: auto-trigger balance recovery or emergency lock

### 2.2 Joint Angle Over-Travel Lock
- AS5600 absolute encoder full-range monitoring
- Software limit + mechanical hard limit dual protection

### 2.3 Sole Contact Surface Loss Warning
- Sole array pressure sensor real-time monitoring of contact status
- Detects loss of contact: immediately adjust ankle or trigger alarm

### 2.4 Upper/Lower Body Time-Division Hardware Interlock
- **Core safety mechanism**: Independent hardware circuit for physical interlock
- Upper body action -> Lower body forced lock
- Lower body walking -> Upper body power circuit forced off
- Eliminates risk of simultaneous action causing center-of-gravity loss

### 2.5 Hose Anti-Burst Protection
- Pop-type anti-burst valve on each upper limb joint
- Instant auto-lock on hose burst, prevents load falling

### 2.6 Quick Release
- Three-point quick-release belt supports 1-second release
- Human body can quickly detach from exoskeleton in emergency

## 3. Safety Design Principles

1. **Fail-Safe** - Any single point fault does not lead to dangerous state
2. **Multiple Redundancy** - Key safety functions have at least two independent layers of protection
3. **Physical Isolation** - Upper/lower body hydraulic systems completely independent, faults do not propagate
4. **Hardware First** - Core safety mechanisms implemented in hardware, not dependent on software