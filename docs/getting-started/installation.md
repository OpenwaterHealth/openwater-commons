# Installation Guide

Complete installation instructions for Openwater platforms.

---

## Prerequisites

- **Python:** 3.8 or higher
- **Operating System:** Windows 10+, macOS 10.14+, Ubuntu 20.04+
- **Hardware:** USB port for device connection

---

## OpenLIFU Installation

### 1. Install Python Package

```bash
# Basic installation
pip install openlifu

# With optional dependencies
pip install openlifu[slicer,sim]
```

### 2. Verify Installation

```bash
python -c "import openlifu; print(openlifu.__version__)"
```

### 3. Install 3D Slicer Extension (Optional)

1. Open 3D Slicer
2. Go to Extension Manager
3. Search for "OpenLIFU"
4. Click Install
5. Restart Slicer

---

## OpenMOTION Installation

### 1. Install Python Package

```bash
pip install openmotion
```

### 2. Install Drivers (Windows only)

Download and install USB serial drivers from:
https://www.silabs.com/developers/usb-to-uart-bridge-vcp-drivers

### 3. Verify Installation

```bash
python -c "import openmotion; print(openmotion.__version__)"
```

---

## Development Installation

For contributing to Openwater:

```bash
# Clone repository
git clone https://github.com/OpenwaterHealth/OpenLIFU-python.git
cd OpenLIFU-python

# Install in editable mode
pip install -e .[dev]

# Run tests
pytest
```

---

## Troubleshooting

### Common Issues

**ImportError: No module named 'openlifu'**
- Ensure pip installation completed successfully
- Check Python version: `python --version`

**Serial port not found**
- Check device is connected
- Linux: Add user to dialout group: `sudo usermod -a -G dialout $USER`
- macOS: Device appears as `/dev/cu.usbserial-*`
- Windows: Check Device Manager for COM port

**Permission denied on Linux**
```bash
sudo usermod -a -G dialout $USER
# Log out and back in
```

---

## Next Steps

- [Quick Start Guide](quickstart.md)
- [First Contribution](first-contribution.md)
- [Hardware Setup](hardware-setup.md)

---

**Need help?** [Open an issue](https://github.com/OpenwaterHealth/openwater-commons/issues) or join [discussions](https://github.com/OpenwaterHealth/openwater-commons/discussions).
