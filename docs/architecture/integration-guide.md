# Integration Guide

**How to integrate Openwater platforms with your applications and workflows**

---

## 🎯 Integration Options

### 1. Python API Integration
Direct integration using OpenLIFU-python or OpenMOTION-Pylib

### 2. 3D Slicer Extension
Use SlicerOpenLIFU for medical imaging workflows

### 3. Command-Line Interface
Batch processing and automation

### 4. Custom Applications
Build standalone applications on our platform

---

## 📚 Python API Integration

### Basic OpenLIFU Usage

```python
from openlifu import db, protocol, plan

# Load hardware configuration
transducer = db.load_transducer("H-317")

# Create treatment protocol
prot = protocol.FUSProtocol(
    pulse_duration=0.01,  # 10ms
    pulse_interval=1.0,    # 1Hz
    num_pulses=100
)

# Plan treatment
target_coords = [10, 20, 30]  # mm from origin
plan = plan.focus_plan(target_coords, transducer, prot)

# Execute
plan.execute()
```

### Basic OpenMOTION Usage

```python
from openmotion import sensor, analysis

# Connect to sensor
device = sensor.MotionSensor(port='/dev/ttyUSB0')

# Stream data
for frame in device.stream():
    motion = analysis.compute_motion(frame)
    blood_flow = analysis.compute_flow(frame)
    print(f"Motion: {motion}, Flow: {blood_flow}")
```

---

## 🔌 Hardware Communication

### Serial Protocol

**Connection:**
- USB Serial
- Baud rate: 115200
- Data bits: 8, Parity: None, Stop bits: 1

**Command Format:**
```
<CMD> <PARAM1> <PARAM2> ... \n
```

**Example:**
```python
import serial

ser = serial.Serial('/dev/ttyUSB0', 115200)
ser.write(b'SET_FREQ 500000\n')  # 500kHz
response = ser.readline()
```

---

## 📦 Installing Dependencies

```bash
# OpenLIFU
pip install openlifu

# OpenMOTION
pip install openmotion

# 3D Slicer Extension
# Install via Slicer Extension Manager
```

---

## 🔗 Further Reading

- [API Reference](../../openwater-docs/docs/developer-guide/api-reference.md)
- [Example Projects](../getting-started/examples/)
- [Troubleshooting](../getting-started/troubleshooting.md)

---

_For detailed integration support, join our [community discussions](https://github.com/OpenwaterHealth/openwater-commons/discussions)._
