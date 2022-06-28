# ESPHome YAML Files

This folder contains the YAML code for the ESPHome Motion Detectors.  

By default, if you use the ESPHome wizard, the top sections of the files will be auto-generated for you (e.g. wifi credentials, etc.).  If this is the case, you only need to add the code for the binary_sensor and switch to this generated code.  If you change the name for the binary sensor, you must also update the automations to use this new name.  Technically, the siwtch entity is optional but recommended.  This gives you a way to reboot the controller from Home Assistant if needed without power cycling the device.  This is especially handy if the power supply to your motion controls isn't readily accessible.

If you manually create the ESPHome YAML, then update the wifi SSID and password to match your environment.  Update any other optional passwords, or leave blank for no password.

### Other notes
The provided code is for a Wemos D1 mini with the motion detector connected to pin D6 (GPIO 12).  If you use a different board or GPIO pin, be sure to update the ESPHome code accordingly.  See the [ESPHome Official Site](https://esphome.io/index.html) for additional information or other options.

### Testing
I recommend that after you build your motion detectors and upload your ESPHome code, you test the sensors before installing.  The easiest way to test is to power up the motion detectors and open the Developer Tools in Home Assistant and select the States tab.

![test_motion](https://user-images.githubusercontent.com/55962781/176053522-59de0cba-2749-401a-af24-ad573af78cd4.jpg)

Filter the entitites by entering the beginning part of your binary sensor name(s) (binary_sensor.stair_motion if you used the defaults - if you used a different name, substitute that until you see your sensors).  Wave your hand or move in front of the motion detectors.  The state should change from "off" to "on", then return to "off" a few seconds after motion stops.  If this occurs, then everything is good with the motion detectors and they are ready to install.  If the state does not change (remains off), then check your wiring on the controller and assure you are using the same GPIO pin on the controller as stated in the ESPHome YAML.

If the state shows "unavailable", Home Assistant cannot see the sensors.  Check your ESPHome code and the wiring of the device(s).
