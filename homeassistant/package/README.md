# Package File

Packages are completely self-contained yaml files that provide the convenience of all entity types in one file that can just be dropped into your Home Assistant configuration as opposed to separate sections or files for input_booleans, timers, automations, etc.  

If you already have packages !included as a directory/folder in your main configuration.yaml file, then you can just download this .yaml file directly into your packages folder and as long as you have not changed the name of your ESPHome binary sensors (binary_sensor.stair_motion_top and binary_sensor.stair_motion_bottom) or your WLED light entity (light.stair_lights), then you do not even have to edit the package .yaml file.  Just restart Home Assistant (and as long as your devices are built, integrated and online), it should 'just work'!

If you haven't enabled packages and have some comfort level with yaml files, you can easily enable packages by completing the following steps:

1. Add a packages folder to your \config folder in your Home Assistant installation:

![package_folder](https://user-images.githubusercontent.com/55962781/176063861-29fa8f9e-006c-4f18-a7ab-d58ecdb65dad.jpg)

(You can name this folder anything you like, but substitute the name you used in the next step)

2. Open your configuration.yaml file and add the following line somewhere under the top `homeassistant:` header:
```
homeassistant:
...
  packages: !include_dir_named packages
...
```

3. Be sure to indent the 'packages' line by **exactly two spaces** and substitute the name of your folder at the end of the line if you named it something different.  Check your configuration file and restart Home Assistant using the Developer Tools YAML tab.

Once packages are enabled, you can simply download and drop the package file included in this folder into your /packages folder.  If you did rename any of your entities, you will need to edit the package .yaml file to update those names.  Otherwise, you can just restart Home Assistant and all necessary helpers and automations will be installed and ready to use.  Otherwise, you do not need any of the other yaml within this repository (except the binary_sensor and switch sections of the ESPHome files).

Note that you can use both packages and split configuration files at the same time.  The only caveat is you cannot duplicate an entity name in a package and in your other configuration files (e.g. if a package has an entity called 'sensor.my_sensor', your other configuration files cannot also have a sensor with this same name).

If you want to see the package process in more detail, please see the following video: [Home Assistant MQTT Changes & Moving to Packages](https://youtu.be/VhHzBXYkVhw). If you wish to skip the section on upcoming MQTT changes in Home Assistant, use the time links or jump to about the 10:00 minute mark in the video to see the step-by-step process for enabling and using packages.
