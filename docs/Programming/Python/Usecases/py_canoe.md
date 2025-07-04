# 🛶 py_canoe

**py_canoe** is a Python package for automating and controlling Vector CANoe 🛶 directly from your scripts. It makes CANoe automation simple for testing, diagnostics, signals, logging, and more.

---

## 🚀 Quick Start

```python
from py_canoe import CANoe, wait
canoe = CANoe()
```

---

## ⚡ Main Features & Examples

### 📂 Open, Start, Stop, Quit

```python
canoe.open(canoe_cfg=r'tests\demo_cfg\demo.cfg')
canoe.start_measurement()
canoe.stop_measurement()
canoe.quit()
```

### 🔎 Get CANoe Version

```python
version = canoe.get_canoe_version_info()
```

### 🔄 Restart/Reset Measurement

```python
canoe.reset_measurement()
canoe.stop_ex_measurement()
```

### 🕹️ Offline Mode: Animation, Step, Reset

```python
canoe.open(r'tests\demo_cfg\demo_offline.cfg')
canoe.add_offline_source_log_file(r'tests\demo_cfg\Logs\demo_log.blf')
canoe.start_measurement_in_animation_mode(animation_delay=200)
wait(1)
canoe.break_measurement_in_offline_mode()
wait(1)
canoe.step_measurement_event_in_single_step()
wait(1)
canoe.reset_measurement_in_offline_mode()
wait(1)
canoe.stop_measurement()
```

### 🔢 Get/Set Measurement Index

```python
idx = canoe.get_measurement_index()
canoe.set_measurement_index(idx + 1)
```

### 💾 Save Config to New Version/Name

```python
canoe.save_configuration_as(path=r'tests\demo_cfg\demo_v10.cfg', major=10, minor=0, create_dir=True)
```

### 📊 CAN Bus Statistics

```python
canoe.get_can_bus_statistics(channel=1)
```

### 🚦 Get/Set Signal Value

```python
sig_full = canoe.get_signal_full_name('CAN', 1, 'LightState', 'FlashLight')
val = canoe.get_signal_value('CAN', 1, 'LightState', 'FlashLight')
canoe.set_signal_value('CAN', 1, 'LightState', 'FlashLight', 1)
```

### 📝 Write Window: Clear/Read/Write

```python
canoe.enable_write_window_output_file(r'tests\demo_cfg\Logs\write_win.txt')
canoe.clear_write_window_content()
canoe.write_text_in_write_window("hello from py_canoe!")
text = canoe.read_text_from_write_window()
canoe.disable_write_window_output_file()
```

### 🖥️ Switch CANoe Desktops

```python
canoe.ui_activate_desktop('Configuration')
```

### 🏷️ System Variables: Get/Set/Define

```python
canoe.set_system_variable_value('demo::level_two_1::sys_var2', 20)
canoe.set_system_variable_array_values('demo::int_array_var', (0, 1, 2, 3, 4, 5, 6, 7, 8, 9))
val = canoe.get_system_variable_value('demo::level_two_1::sys_var2')
canoe.define_system_variable('sys_demo::demo', 1)
```

### 🛠️ Diagnostics: Send Request, Tester Present

```python
resp = canoe.send_diag_request('Door', 'DefaultSession_Start', False)
canoe.control_tester_present('Door', False)
canoe.control_tester_present('Door', True)
resp = canoe.send_diag_request('Door', '10 02')
```

### ⏯️ Replay Block: Set File, Control

```python
canoe.set_replay_block_file('DemoReplayBlock', r'tests\demo_cfg\Logs\demo_log.blf')
canoe.control_replay_block('DemoReplayBlock', start_stop=True)
canoe.control_replay_block('DemoReplayBlock', start_stop=False)
```

### 🧩 CAPL: Compile & Call Function

```python
canoe.compile_all_capl_nodes()
canoe.call_capl_function('addition_function', 100, 200)
canoe.call_capl_function('hello_world')
```

### 🧪 Test Modules: Execute

```python
canoe.execute_all_test_modules_in_test_env(demo_test_environment)
canoe.execute_test_module('demo_test_node_002')
```

### 🌎 Environment Variables: Get/Set

```python
canoe.set_environment_variable_value('int_var', 123.12)
canoe.set_environment_variable_value('string_var', 'this is string variable')
val = canoe.get_environment_variable_value('int_var')
```

### 🗃️ Database: Add/Remove

```python
canoe.add_database(r'tests\demo_cfg\DBs\sample_databases\XCP.dbc', 'CAN1', 1)
canoe.remove_database(r'tests\demo_cfg\DBs\sample_databases\XCP.dbc', 1)
```

### 🟢 Online Logging Block: Start/Stop

```python
canoe.start_stop_online_measurement_setup_logging_block(r'tests\demo_cfg\Logs\demo_online_setup_log.blf', start=False)
canoe.start_stop_online_measurement_setup_logging_block(r'tests\demo_cfg\Logs\demo_online_setup_log.blf', start=True)
```

### 📦 Logging Blocks: Add/Remove

```python
# Remove all logging blocks
for i in range(canoe.logging_collection.count):
    canoe.remove_logging_block(1)
# Add a new block
canoe.add_logging_block("C:/sample_log_{IncMeasurement}.blf")
```

---

## ❓ Practice Questions

1. How do you open a CANoe configuration and start a measurement?
2. How can you get and set a signal value on a specific CAN channel?
3. What is the method to save a CANoe configuration to a new version?
4. How do you send a diagnostic request and control tester present?
5. How can you add and remove a database from a CANoe configuration?
6. How do you write and read text from the CANoe write window?
7. What steps are needed to compile CAPL nodes and call a CAPL function?
8. How do you get/set environment and system variables in CANoe?
9. How can you control replay blocks and logging blocks during measurement?
10. How do you switch between different CANoe desktops using py_canoe?
