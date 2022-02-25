# UH50 Python package
This module reads from the Landys & Gyr UH50 heat measuring unit and returns the currect GJ and m3 meters.
Note: An (USB) IR reader is needed and connected to the machine running the python script

WARNING: everytime this is called, battery time of the UH50 will go down by about 30 minutes!
This package has been tested with the Landys & Gyr UH50 type LUGCUH50. Other models are likely to work as well.

## Using the python integration

To use the module as a script, call the module directly and follow the instructions through the command line.
To use the module as an API use code, such as:

```python
from uh50_api import uh50

uh50.findports()  # to check available ports

result = uh50.read_uh50('port')  # eg uh50.read_uh50('/dev/ttyUSB0') or uh50.read_uh50('COM5')
print('GJ :',result['gj'])
print('m3 :',result['m3'])
print('model :',result['model'])
print('full response :',result['full_response'])

```