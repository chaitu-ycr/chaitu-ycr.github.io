# 🚗 udsoncan

**udsoncan** is a Python library for communicating with automotive ECUs (Electronic Control Units) using UDS (Unified Diagnostic Services) over CAN. It helps you read, write, reset, unlock, and clear data on vehicle ECUs.

---

## ⚡ Main Use Cases

### 🔌 1. Connect to ECU

Set up a CAN connection to your ECU.

```python
import udsoncan
from udsoncan.connections import PythonIsoTpConnection
import isotp, can

bus = can.interface.Bus(bustype='socketcan', channel='can0', bitrate=500000)
tp_addr = isotp.Address(isotp.AddressingMode.Normal_11bits, txid=0x7E0, rxid=0x7E8)
conn = PythonIsoTpConnection(bus, tp_addr)
```

---

### 📖 2. Read Data (e.g., VIN)

Read specific data like the VIN from the ECU.

```python
from udsoncan.client import Client

with Client(conn, request_timeout=2) as client:
    response = client.read_data_by_identifier(0xF190)  # VIN
    print(response.service_data.values)
```

---

### ✍️ 3. Write Data

Write data to a specific identifier.

```python
with Client(conn, request_timeout=2) as client:
    client.write_data_by_identifier(0xF191, b'\x12\x34')
```

---

### 🔄 4. ECU Reset

Reset the ECU.

```python
from udsoncan.services import ECUReset

with Client(conn, request_timeout=2) as client:
    client.ecu_reset(ECUReset.HardReset)
```

---

### 🔓 5. Security Access

Unlock security-protected ECU functions.

```python
from udsoncan.services import SecurityAccess

with Client(conn, request_timeout=2) as client:
    seed = client.security_access(SecurityAccess.Level1)
    # Calculate key from seed, then send key
    client.security_access(SecurityAccess.Level1 + 1, key=b'\x12\x34\x56\x78')
```

---

### 🛠️ 6. Diagnostic Session Control

Switch between diagnostic sessions.

```python
from udsoncan.services import DiagnosticSessionControl

with Client(conn, request_timeout=2) as client:
    client.diagnostic_session_control(DiagnosticSessionControl.ExtendedDiagnosticSession)
```

---

### 🧹 7. Clear Diagnostic Trouble Codes (DTCs)

Clear all DTCs from the ECU.

```python
from udsoncan.services import ClearDiagnosticInformation

with Client(conn, request_timeout=2) as client:
    client.clear_diagnostic_information(0xFFFFFF)
```

---

**Tip:** Always check your hardware and permissions before running diagnostic commands on a real ECU.

---

## 📝 Practice Questions

1. How do you connect to an ECU using udsoncan?
2. Write a code snippet to read the VIN from an ECU.
3. How can you reset an ECU using udsoncan?
4. What is the purpose of Security Access in UDS?
5. Write an example to clear all DTCs from an ECU.
