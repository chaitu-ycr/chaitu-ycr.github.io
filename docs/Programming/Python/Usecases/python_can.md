# 🚌 python-can

**python-can** is a simple Python library to send, receive, filter, log, and replay CAN (Controller Area Network) messages. It supports many CAN hardware interfaces and makes CAN bus programming easy.

---

## 🚀 Quick Example

```python
import can

with can.Bus(interface='socketcan', channel='can0', bitrate=500000) as bus:
    msg = can.Message(arbitration_id=0x123, data=[1, 2, 3, 4], is_extended_id=False)
    bus.send(msg)
    print("Message sent!")
```

---

## 🧩 Main Features & Examples

### 1️⃣ Create a CAN Bus

```python
bus = can.Bus(interface='socketcan', channel='can0', bitrate=500000)
```

### 2️⃣ Send a Message

```python
msg = can.Message(arbitration_id=0x123, data=[1, 2, 3, 4], is_extended_id=False)
bus.send(msg)
```

### 3️⃣ Receive Messages

```python
msg = bus.recv(timeout=1.0)
print(msg)
```
Or receive in a loop:
```python
for msg in bus:
    print(msg)
```

### 4️⃣ Filter Messages

```python
bus.set_filters([{"can_id": 0x123, "can_mask": 0x7FF}])
```

### 5️⃣ Notifiers & Listeners

```python
reader = can.BufferedReader()
notifier = can.Notifier(bus, [reader])
msg = reader.get_message(timeout=1.0)
```

### 6️⃣ Read & Write Logs

Read log:
```python
log_reader = can.LogReader('logfile.asc')
for msg in log_reader:
    print(msg)
```
Write log (CSV):
```python
csv_writer = can.CSVWriter('output.csv')
csv_writer.on_message_received(msg)
```

### 7️⃣ Replay Messages from Log

```python
log_reader = can.LogReader('logfile.asc')
with can.Bus(interface='socketcan', channel='can0') as bus:
    for msg in log_reader:
        bus.send(msg)
```

### 8️⃣ Asyncio Support

```python
import asyncio
import can

async def main():
    bus = can.AsyncBufferedReader()
    msg = await bus.get_message()
    print(msg)
```

### 9️⃣ Error Handling

```python
try:
    bus.send(msg)
except can.CanError:
    print("Send failed")
```

### 🔟 Send Periodic Messages

```python
bm = can.BroadcastManager(bus, msg, period=0.1)
```

---

## 🛠️ Other Utilities

- Message serialization/deserialization
- Timestamp handling
- Logging helpers

---

## ❓ Practice Questions

1. How do you send a CAN message with an extended ID?
2. Write code to filter only messages with arbitration ID `0x321`.
3. How can you read messages from a `.asc` log file and print them?
4. What is the purpose of `can.Notifier`?
5. How do you handle errors when sending messages?
6. Write a short script to send a message every 0.5 seconds.
7. How do you use asyncio with python-can?
