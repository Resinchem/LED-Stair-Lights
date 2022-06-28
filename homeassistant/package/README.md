# Package File

Packages are completely self-contained yaml files that provide the convenience of all entity types in one file that can just be dropped into your Home Assistant configuration as opposed to separate sections or files for input_booleans, timers, automations, etc.  

If you already have packages !included as a directory/folder in your main configuration.yaml file, then you can just download this .yaml file directly into your packages folder and as long as you have not changed the name of your ESPHome binary sensors (binary_sensor.stair_motion_top and binary_sensor.stair_motion_bottom) or your WLED light entity (light.stair_lights), then you do not even have to edit the package .yaml file.  Just reload your automations (and as long as your devices are built, integrated and online), it should 'just work'!

If you haven't enabled packages and have some comfort level with yaml files, you can easily enable packages by completing the following steps:

1. Add a packages folder to your \config folder in your Home Assistant installation:

