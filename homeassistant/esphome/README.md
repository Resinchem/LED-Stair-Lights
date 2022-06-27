# ESPHome YAML Files

This folder contains the YAML code for the ESPHome Motion Detectors.  

By default, if you use the ESPHome wizard, the top sections of the files will be auto-generated for you (e.g. wifi credentials, etc.).  If this is the case, you only need to add the code for the binary_sensor and switch to this generated code.  If you change the name for the binary sensor, you must also update the automations to use this new name.

If you manually create the ESPHome YAML, then update the wifi SSID and password to match your environment.  Update any other optional passwords, or leave blank for no password.

### Other notes
The provided code is for a Wemos D1 mini with the motion detector connected to pin D6 (GPIO 12).  If you use a different board or GPIO pin, be sure to update the ESPHome code accordingly.  See the [ESPHome Official Site](https://esphome.io/index.html) for additional information or other options.

### Testing
I recommend that after you build your motion detectors and upload your ESPHome code, you test the sensors before installing.  The easiest way to test is to power up the motion detectors and open the Developer Tools in Home Assistant and select the States tab.

