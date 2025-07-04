# 🚗 `cantools`

## 🌟 Overview

`cantools` is a Python library for working with CAN message databases (DBC files). It simplifies CAN communication by providing tools for parsing DBC files, encoding/decoding messages, and generating C code for embedded systems.

### ✨ Key Features
- **DBC Parsing**: Load and extract information about messages, signals, and nodes.
- **Message Encoding/Decoding**: Convert Python data structures to CAN messages and vice versa.
- **C Code Generation**: Generate C code for CAN message packing/unpacking.
- **Diagnostic Message Handling**: Decode/encode diagnostic messages (e.g., J1939).
- **CLI Tools**: Monitor live CAN bus traffic with `candump`.

### 🚀 Installation
```bash
pip install cantools
```

---

## 🛠️ Use Cases with Examples

### 1️⃣ Load CAN Database and Print Nodes/Messages
```python
import cantools

db_obj = cantools.db.load_file('./_data/can_powertrain.dbc')

print('Nodes:', [node.name for node in db_obj.nodes])
print('Messages:', [msg.name for msg in db_obj.messages])
```

---

### 2️⃣ Extract Messages and Signals to CSV
```python
import cantools
import pandas as pd

db_obj = cantools.db.load_file('./_data/can_powertrain.dbc')

data = [
    {'message_name': msg.name, 'message_id': msg.frame_id, 'signal_name': sig.name}
    for msg in db_obj.messages for sig in msg.signals
]

pd.DataFrame(data).to_csv('./_output/messages_signals.csv', index=False)
```

---

### 3️⃣ Decode CAN Log File and Plot Signal
```python
import can
import cantools
import pandas as pd
import plotly.express as px

db_obj = cantools.db.load_file('./_data/can_powertrain.dbc')
can_log_data = can.BLFReader('./_data/can_log_file.blf')

engine_data = [
    {'timestamp': msg.timestamp, 'EngSpeed': db_obj.decode_message(msg.arbitration_id, msg.data).get('EngSpeed', 0)}
    for msg in can_log_data if msg.channel == 1 and msg.arbitration_id == 100
]

df = pd.DataFrame(engine_data)
fig = px.line(df, x='timestamp', y='EngSpeed', title='Engine Speed')
fig.show()
```

---

### 4️⃣ Generate C Code for CAN Communication
```python
import cantools

db_obj = cantools.db.load_file('./_data/can_powertrain.dbc')
db_obj.generate_c_source('./_output/c_code')

print('C code generated successfully!')
```

---

### 5️⃣ Monitor Live CAN Bus Traffic (CLI)
Run the following command in the terminal:
```bash
candump -d ./_data/can_powertrain.dbc
```

---

## 📝 Practice Questions

1. **DBC Parsing**: Write a script to load a DBC file and print all signal names for each message.
2. **Signal Extraction**: Extract all signals from a DBC file and save them to a JSON file instead of CSV.
3. **Log Analysis**: Decode a CAN log file and plot multiple signals (e.g., engine speed and temperature).
4. **C Code Generation**: Generate C code for a given DBC file and explain its usage in embedded systems.
5. **CLI Usage**: Use `candump` to monitor live CAN traffic and decode messages.
