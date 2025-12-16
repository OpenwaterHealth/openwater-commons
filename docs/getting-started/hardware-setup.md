# Hardware Setup Guide

Setting up Openwater hardware for development and use.

---

## 🔌 OpenLIFU Hardware Setup

### Components

- LIFU transducer
- Ultrasound driver electronics
- Control computer (USB connection)
- Power supply

### Setup Steps

1. **Connect Power**
   - Connect 24V power supply
   - Verify power LED

2. **Connect USB**
   - Connect USB cable to computer
   - Install drivers if needed (Windows)

3. **Verify Connection**
   ```bash
   python -c "from openlifu import hardware; hardware.list_devices()"
   ```

4. **Run Test**
   ```bash
   python examples/hardware_test.py
   ```

---

## 📡 OpenMOTION Hardware Setup

### Components

- Motion sensor module
- Console unit
- USB cable
- Power adapter

### Setup Steps

1. **Connect Sensor**
   - Attach sensor to console
   - Verify LED indicators

2. **Connect to Computer**
   - USB cable to console
   - Install drivers (Windows only)

3. **Test Connection**
   ```python
   from openmotion import sensor
   device = sensor.MotionSensor()
   print(device.is_connected())
   ```

---

## 🔧 Troubleshooting

### Device Not Detected

**Linux:**
```bash
# Check device appears
ls /dev/ttyUSB*

# Add user to dialout group
sudo usermod -a -G dialout $USER
# Log out and back in
```

**macOS:**
```bash
# Check device
ls /dev/cu.usbserial-*
```

**Windows:**
- Check Device Manager for COM ports
- Install/update USB serial drivers

### No Response from Device

1. Check power LED
2. Try different USB port
3. Restart device
4. Check cables

---

## 📚 Hardware Documentation

- [Mechanical Design](../hardware-guide/mechanical-design/)
- [Electrical Design](../hardware-guide/electrical-design/)
- [Assembly Guides](https://github.com/OpenwaterHealth/OpenLIFU-assembly-guides)

---

**Need help?** [Open an issue](https://github.com/OpenwaterHealth/openwater-commons/issues) with label `hardware`.
