# cantools

## intro

- In the world of Python and Controller Area Network (CAN) buses, `cantools` shines as a powerful library designed specifically for working with CAN message databases (DBC files).
- It offers functionalities for parsing these databases, encoding and decoding CAN messages, and even generating C code for interacting with CAN buses.
- Purpose
    - `cantools` simplifies working with CAN messages by providing tools to handle DBC files, a common format for specifying CAN bus communication protocols.
    - It acts as a bridge between the human-readable DBC format and the raw CAN message data used by CAN bus controllers.
- Key Features
    - DBC Parsing
        - Loads and parses DBC files, extracting information about messages, signals, nodes, and network configurations.
    - Message Encoding and Decoding
        - Encodes Python data structures into CAN messages based on DBC specifications and decodes received CAN messages back into Python objects.
    - C Code Generation
        - Generates C source code that can be used to interact with CAN buses, including message packing and unpacking functions.
    - Diagnostic Message Handling
        - Supports decoding and encoding of diagnostic messages defined in DBC files using the J1939 standard.
    - Command Line Interface (CLI)
        - Provides a command-line tool (`candump`) for monitoring live CAN bus traffic and decoding messages based on a DBC file.
- Benefits of Using `cantools`
    - Simplified CAN Message Handling
        - Abstracts the complexities of DBC file structure and CAN message details, making it easier to work with CAN communication.
    - Efficient Data Encoding and Decoding
        - Streamlines the process of converting between Python data and CAN message representations.
    - C Code Generation for Embedded Systems
        - Enables integration of CAN communication functionalities into C-based embedded systems projects.
    - Live Bus Monitoring:
        - The `candump` tool aids in debugging and analyzing CAN bus traffic.
- Common Use Cases
    - Developing CAN bus applications in Python
        - Parse DBC files, encode/decode messages, and interact with CAN buses for data acquisition, control, and monitoring.
    - Testing and Debugging CAN communication:
        - Use `candump` to monitor live bus traffic and verify message formats based on DBC specifications.
    - Reverse Engineering CAN bus protocols
        - Analyze existing DBC files to understand the communication patterns of a CAN bus system.
    - Generating C code for CAN communication in embedded systems
        - Leverage the code generation feature to integrate CAN functionalities into C projects.
- Relationship with `python-can`
    - `cantools` complements python-can by focusing on the message definition and data aspects of CAN communication using DBC files.
    - `python-can` handles the low-level details of sending and receiving CAN messages on the physical bus.
- package installation command

    ```bash
    pip install cantools
    ```

## examples based on usecase

### load CAN database and print nodes and messages

```python
import cantools

database_file_powertrain = './_data/can_powertrain.dbc'

db_obj_powertrain = cantools.db.load_file(database_file_powertrain)

print('Nodes')
for node in db_obj_powertrain.nodes:
    print(f'    {node.name}')
print('Messages')
for msg in db_obj_powertrain.messages:
    print(f'    {msg.name}')
```

### load CAN database and extract all messages and its signals into csv

```python
import cantools
import pandas as pd

database_file_comfort = './_data/can_comfort.dbc'
database_file_powertrain = './_data/can_powertrain.dbc'

csv_export_file_comfort = './_output/csv_comfort.csv'
csv_export_file_powertrain = './_output/csv_powertrain.csv'

db_obj_comfort = cantools.db.load_file(database_file_comfort)
db_obj_powertrain = cantools.db.load_file(database_file_powertrain)

dict_comfort = {'message_name': list(), 'message_id': list(), 'signal_name': list()}
dict_powertrain = {'message_name': list(), 'message_id': list(), 'signal_name': list()}

for msg in db_obj_comfort.messages:
    for sig in msg.signals:
        dict_comfort['message_name'].append(msg.name)
        dict_comfort['message_id'].append(msg.frame_id)
        dict_comfort['signal_name'].append(sig.name)
for msg in db_obj_powertrain.messages:
    for sig in msg.signals:
        dict_powertrain['message_name'].append(msg.name)
        dict_powertrain['message_id'].append(msg.frame_id)
        dict_powertrain['signal_name'].append(sig.name)

dataframe_comfort = pd.DataFrame.from_dict(dict_comfort)
dataframe_powertrain = pd.DataFrame.from_dict(dict_powertrain)

dataframe_comfort.to_csv(csv_export_file_comfort)
dataframe_powertrain.to_csv(csv_export_file_powertrain)
```

### from can log file extract can message signals information to csv and plot one signal

```python
import can
import cantools
import pandas as pd
import plotly.express as px

database_file_powertrain = './_data/can_powertrain.dbc'
can_log_file = './_data/can_log_file.blf'   # CAN channel 1 has powertrain data and CAN channel 0 has comfort data

can_log_file_data_obj = can.BLFReader(can_log_file)

db_obj_powertrain = cantools.db.load_file(database_file_powertrain)

engine_message_id = 100
engine_message_data = {'message_timestamp': list()}
for msg in can_log_file_data_obj:
    if msg.channel == 1 and msg.arbitration_id == engine_message_id:
        decoded_message_data = db_obj_powertrain.decode_message(msg.arbitration_id, msg.data, decode_choices=False)
        engine_message_data['message_timestamp'].append(msg.timestamp)
        for signal_name, signal_value in decoded_message_data.items():
            if signal_name not in engine_message_data.keys():
                engine_message_data[signal_name] = list()
            engine_message_data[signal_name].append(signal_value)

dataframe_engine_message = pd.DataFrame.from_dict(engine_message_data)

# export powertrain engine message to csv file
csv_export_file_engine_message = './_output/csv_engine_message.csv'
dataframe_engine_message.to_csv(csv_export_file_engine_message)

# plot engine speed from powertrain engine message
fig = px.line(dataframe_engine_message, x='message_timestamp', y='EngSpeed', title='Engine Speed')
fig.show()
```