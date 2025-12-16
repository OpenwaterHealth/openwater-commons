# Quick Start Guide

Get up and running with Openwater in 5 minutes.

---

## 🚀 OpenLIFU Quick Start

### 1. Install Python Package

```bash
pip install openlifu
```

### 2. Run Your First Script

```python
from openlifu import db, protocol

# Load a transducer
transducer = db.load_transducer("H-317")

# Create a simple protocol
prot = protocol.FUSProtocol(
    pulse_duration=0.01,
    pulse_interval=1.0,
    num_pulses=10
)

print(f"Transducer: {transducer.name}")
print(f"Protocol: {prot.num_pulses} pulses")
```

### 3. Next Steps

- [Full Installation Guide](installation.md)
- [First Contribution Guide](first-contribution.md)
- [Hardware Setup](hardware-setup.md)

---

## 🎯 OpenMOTION Quick Start

### 1. Install Python Package

```bash
pip install openmotion
```

### 2. Connect to Sensor

```python
from openmotion import sensor

device = sensor.MotionSensor(port='/dev/ttyUSB0')
print(f"Connected: {device.is_connected()}")
```

### 3. Next Steps

- [OpenMOTION Documentation](../../openwater-docs/docs/user-guide/openmotion/)
- [Hardware Setup](hardware-setup.md)

---

## 📚 Resources

- [Documentation](https://docs.openwater.health)
- [API Reference](../../openwater-docs/docs/developer-guide/api-reference.md)
- [Examples](https://github.com/OpenwaterHealth/OpenLIFU-examples)
- [Community](https://github.com/OpenwaterHealth/openwater-commons/discussions)

---

**Need help?** Join our [community discussions](https://github.com/OpenwaterHealth/openwater-commons/discussions)!
