This is a fork from https://github.com/MrLeeh/pyads
More information can be found there.

Tested using TwinCAT3 and Python3 on Windows.

## Installation

```bash
pip install pyads 
```
### Windows
Make sure that you have the `TcAdsDll.dll` provided by Beckhoff installed on your PATH.

## Usage

Run TwinCAT3 with a boolean variable 'test' is TRUE.

```python
>>> import pyads
>>> pyads.open_port()
32866
>>> pyads.get_local_address()
<AmsAddress 10.123.66.28.1.1:32866>
>>> adr = pyads.AmsAddr('10.123.66.28.1.1', 851)
>>> pyads.read_device_info(adr)
('Plc30 App', <pyads.structs.AdsVersion object at 0x0000000002898278>)
>>> pyads.read_by_name(adr, 'MAIN.test', pyads.PLCTYPE_BOOL)
True
```

The AmsNetId is the same (10.123.66.28) because it's running in the same computer.
