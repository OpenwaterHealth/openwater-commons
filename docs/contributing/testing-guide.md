# Testing Guide

How to write and run tests for Openwater projects.

---

## 🧪 Testing Philosophy

- Write tests for new features
- Test edge cases
- Keep tests simple and clear
- Run tests before committing

---

## 🐍 Python Testing (pytest)

### Running Tests

```bash
# All tests
pytest

# Specific file
pytest tests/test_protocol.py

# With coverage
pytest --cov=openlifu
```

### Writing Tests

```python
import pytest
from openlifu import protocol

def test_protocol_creation():
    """Test basic protocol creation"""
    prot = protocol.FUSProtocol(
        pulse_duration=0.01,
        pulse_interval=1.0,
        num_pulses=10
    )
    assert prot.num_pulses == 10
    assert prot.pulse_duration == 0.01

def test_invalid_protocol():
    """Test protocol validation"""
    with pytest.raises(ValueError):
        protocol.FUSProtocol(pulse_duration=-1)
```

---

## 🔧 Firmware Testing (Unity)

### Running Tests

```bash
cd firmware
make test
```

### Writing Tests

```c
#include "unity.h"
#include "waveform.h"

void test_waveform_generation(void) {
    float freq = 500000.0;  // 500kHz
    Waveform* wf = generate_waveform(freq);
    
    TEST_ASSERT_NOT_NULL(wf);
    TEST_ASSERT_EQUAL_FLOAT(freq, wf->frequency);
}
```

---

## 🔌 Hardware Testing

### Test Fixtures

- Use test fixtures for hardware validation
- Document test procedures
- Record calibration data

### Example Test

```python
def test_hardware_communication():
    """Test serial communication with device"""
    device = hardware.connect()
    response = device.send_command("STATUS")
    assert "OK" in response
    device.disconnect()
```

---

## 📊 Test Coverage

**Goals:**
- Core functionality: >90% coverage
- Utilities: >80% coverage
- Overall: >70% coverage

**Check coverage:**
```bash
pytest --cov=openlifu --cov-report=html
open htmlcov/index.html
```

---

## 🚨 Continuous Integration

Tests run automatically on:
- Every pull request
- Every commit to main
- Nightly builds

**All tests must pass before merge.**

---

## 💡 Testing Tips

1. **Test one thing:** Each test should verify one behavior
2. **Use descriptive names:** `test_protocol_rejects_negative_duration`
3. **Arrange-Act-Assert:** Setup, execute, verify
4. **Mock hardware:** Use mocks for hardware tests
5. **Test edge cases:** Empty inputs, max values, invalid data

---

**Questions?** See [examples](https://github.com/OpenwaterHealth/OpenLIFU-python/tree/main/tests) or ask in [discussions](https://github.com/OpenwaterHealth/openwater-commons/discussions).
