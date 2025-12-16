# Openwater System Architecture Overview

**Last Updated:** December 2025  
**Audience:** Developers, System Integrators, Technical Partners

---

## 🏗️ Platform Overview

Openwater is an open-source platform for medical imaging and therapeutic ultrasound, consisting of two main product lines:

1. **OpenLIFU** - Low Intensity Focused Ultrasound (neuromodulation, brain stimulation)
2. **OpenMOTION** - Motion tracking and blood flow imaging

Both platforms share common architectural principles and integration patterns.

---

## 🎯 High-Level Architecture

```
┌─────────────────────────────────────────────────────────────┐
│                   User Applications                          │
│  (3D Slicer, Custom Apps, Research Tools, Clinical Systems) │
└──────────────────┬──────────────────────────────────────────┘
                   │
┌──────────────────▼──────────────────────────────────────────┐
│              Software Layer (Python/C++)                     │
│  • OpenLIFU-python (LIFU control & planning)                │
│  • OpenMOTION-Pylib (Motion data acquisition)               │
│  • SlicerOpenLIFU (3D Slicer integration)                   │
└──────────────────┬──────────────────────────────────────────┘
                   │
┌──────────────────▼──────────────────────────────────────────┐
│            Firmware Layer (Embedded C/C++)                   │
│  • LIFU transmitter firmware                                 │
│  • Motion sensor firmware                                    │
│  • Motion console firmware                                   │
└──────────────────┬──────────────────────────────────────────┘
                   │
┌──────────────────▼──────────────────────────────────────────┐
│              Hardware Layer                                  │
│  • Ultrasound transducers & drivers                         │
│  • Motion sensors & tracking                                 │
│  • Laser systems (blood flow)                               │
│  • Power supplies & control electronics                      │
└─────────────────────────────────────────────────────────────┘
```

---

## 🧩 Component Architecture

### Software Layer

#### OpenLIFU-python
**Purpose:** Core Python toolbox for ultrasound planning and control

**Key Components:**
- **Pulse Sequence Library:** Pre-defined ultrasound protocols
- **Treatment Planning:** Target definition, trajectory planning
- **Hardware Interface:** Communication with firmware layer
- **Simulation:** K-Wave integration for acoustic modeling
- **Imaging Integration:** DICOM/NIfTI handling, registration

**Dependencies:**
- Python 3.8+
- NumPy, SciPy
- SimpleITK (medical imaging)
- K-Wave (acoustic simulation, optional)
- PySerial (hardware communication)

**Key APIs:**
```python
from openlifu import db, protocol, plan, sim, seg, xdc

# Define transducer
transducer = db.load_transducer("H-317")

# Create protocol
protocol = protocol.FUSProtocol(...)

# Plan treatment
plan = plan.focus_plan(target, transducer, protocol)

# Execute
plan.execute()
```

#### SlicerOpenLIFU
**Purpose:** 3D Slicer extension for visualization and treatment planning

**Key Features:**
- Interactive target selection
- Real-time trajectory planning
- Skull registration
- Treatment simulation
- Hardware integration

**Integration:**
- Extends 3D Slicer's medical imaging platform
- Uses OpenLIFU-python as backend
- MRML scene integration
- Custom widgets for LIFU-specific functions

#### OpenMOTION-Pylib
**Purpose:** Python library for motion tracking and blood flow imaging

**Key Components:**
- **Data Acquisition:** Real-time sensor data streaming
- **Signal Processing:** Motion artifact correction
- **Blood Flow Analysis:** Optical flow quantification
- **Visualization:** Real-time display

**Dependencies:**
- Python 3.8+
- NumPy, OpenCV
- PySerial (hardware communication)
- Matplotlib (visualization)

---

### Firmware Layer

#### LIFU Transmitter Firmware
**Purpose:** Control ultrasound waveform generation

**Platform:** STM32 microcontroller  
**Language:** C/C++

**Key Modules:**
- Waveform synthesis
- Trigger timing control
- Safety monitoring
- Serial communication (control from Python)
- Power regulation

**Communication Protocol:**
- Serial over USB (115200 baud)
- Command-response architecture
- Binary protocol for waveforms
- ASCII for configuration

#### Motion Firmware
**Purpose:** Motion sensor data acquisition and streaming

**Platform:** ESP32 or similar  
**Language:** C/C++

**Key Modules:**
- IMU data acquisition
- Optical sensor interface
- Real-time streaming
- WiFi/Bluetooth communication
- Calibration routines

---

### Hardware Layer

#### OpenLIFU Hardware

**Mechanical:**
- Transducer mounting systems
- Patient positioning
- Stereotactic frame integration
- MRI-compatible materials

**Electrical:**
- High-voltage ultrasound drivers
- Timing control circuits
- Safety interlocks
- Power distribution

**See:** [Hardware Design Guidelines](../hardware-guide/design-principles.md)

#### OpenMOTION Hardware

**Mechanical:**
- Sensor mounting
- Optical path design
- Patient interface

**Electrical:**
- LED drivers
- Photodetector amplifiers
- ADC circuits
- Processing unit

---

## 🔌 Integration Patterns

### Pattern 1: 3D Slicer Integration

```
User Interface (3D Slicer)
    │
    ▼
SlicerOpenLIFU Extension
    │
    ▼
OpenLIFU-python API
    │
    ▼
Serial Communication
    │
    ▼
LIFU Firmware
    │
    ▼
Hardware
```

**Data Flow:**
1. User selects target in Slicer 3D view
2. SlicerOpenLIFU calls OpenLIFU-python for planning
3. Python computes waveforms and sends to firmware
4. Firmware controls hardware
5. Feedback data flows back up to visualization

### Pattern 2: Standalone Research Application

```
Custom Python Script
    │
    ▼
OpenLIFU-python / OpenMOTION-Pylib
    │
    ▼
Hardware
```

**Use Cases:**
- Batch processing
- Automated experiments
- Continuous monitoring
- Custom protocols

### Pattern 3: Cloud Services (Future)

```
Web Application
    │
    ▼
Cloud API (REST/GraphQL)
    │
    ▼
Processing Service
    │
    ▼
Local Agent
    │
    ▼
Hardware
```

**Future Capabilities:**
- Remote monitoring
- Cloud-based planning
- Multi-site coordination
- Data aggregation

---

## 🗄️ Data Flow & Storage

### Data Types

**Medical Imaging:**
- CT/MRI scans (DICOM, NIfTI)
- Ultrasound images
- 3D meshes (STL, OBJ)

**Treatment Data:**
- Target coordinates
- Pulse sequences
- Acoustic parameters
- Safety thresholds

**Sensor Data:**
- Motion tracking (IMU)
- Blood flow (optical)
- Physiological monitoring

**Metadata:**
- Patient identifiers (anonymized)
- Session logs
- Hardware configurations
- Calibration data

### Storage Architecture

**Local:**
```
project/
├── imaging/          # Medical images
├── plans/            # Treatment plans
├── sessions/         # Session data
├── calibration/      # Hardware calibration
└── logs/             # System logs
```

**Cloud (Future):**
- Anonymized aggregate data
- Research datasets
- Model training data
- Benchmarking results

---

## 🔐 Security Architecture

### Authentication & Authorization
- User authentication (future: LDAP/SSO)
- Role-based access control
- Hardware access controls
- Audit logging

### Data Protection
- Patient data anonymization
- Encryption at rest (AES-256)
- Encryption in transit (TLS)
- HIPAA compliance considerations

### Safety Systems
- Hardware interlocks
- Software watchdogs
- Emergency shutoff
- Parameter validation
- Dose monitoring

---

## 🌐 Network Architecture

### Current State (Standalone)
```
[PC] ←─USB─→ [Firmware] ←─→ [Hardware]
```

**Characteristics:**
- Direct USB connection
- No network required
- Simple, reliable
- Local processing

### Future State (Networked)
```
[Web UI] ←─WiFi─→ [Device] ←─→ [Hardware]
   ↑
   │
   └─Cloud─→ [Central Server]
```

**Planned Features:**
- WiFi connectivity
- Remote monitoring
- Cloud integration
- Multi-device coordination

---

## 🧪 Testing Architecture

### Unit Testing
- Python: pytest framework
- Firmware: Unity framework
- Hardware: Custom test fixtures

### Integration Testing
- End-to-end workflows
- Hardware-in-the-loop testing
- Simulated hardware (mocks)

### Validation Testing
- Acoustic field measurements
- Motion accuracy validation
- Safety system verification
- Regulatory compliance testing

**See:** [Testing Guide](../contributing/testing-guide.md)

---

## 📈 Performance Characteristics

### OpenLIFU
- **Planning Time:** <5 seconds for typical target
- **Control Latency:** <10ms from command to execution
- **Accuracy:** Sub-millimeter targeting
- **Safety Response:** <100ms emergency shutoff

### OpenMOTION
- **Sampling Rate:** 100-1000 Hz (configurable)
- **Data Latency:** <50ms from sensor to display
- **Blood Flow Precision:** ±5% at typical flows
- **Motion Tracking:** ±0.1mm, ±0.5°

---

## 🔮 Future Architecture Evolution

### Near-Term (2026)
- [ ] Cloud services API
- [ ] Multi-user access control
- [ ] Enhanced 3D Slicer integration
- [ ] Real-time collaboration features

### Mid-Term (2027)
- [ ] AI-assisted treatment planning
- [ ] Federated learning infrastructure
- [ ] Mobile applications
- [ ] Continuous monitoring systems

### Long-Term (2028+)
- [ ] Fully autonomous operation
- [ ] Integration with hospital EMR systems
- [ ] Real-time adaptive control
- [ ] Large-scale clinical trial infrastructure

---

## 📚 Related Documentation

- [Integration Guide](integration-guide.md) - Detailed integration patterns
- [API Reference](../../openwater-docs/docs/developer-guide/api-reference.md) - Complete API documentation
- [Hardware Guide](../../openwater-docs/docs/hardware-guide/) - Hardware architecture details
- [Security Policy](../../SECURITY.md) - Security best practices

---

## 🤝 Contributing

See architecture questions or suggestions?
- [Open an issue](https://github.com/OpenwaterHealth/openwater-commons/issues) with label `architecture`
- [Join discussions](https://github.com/OpenwaterHealth/openwater-commons/discussions)
- Propose changes via RFC process

---

**This document is maintained by the Technical Steering Committee.**  
**Last review:** December 2025
