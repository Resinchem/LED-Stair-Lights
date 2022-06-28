# Automations

This folder contains two versions of the automations for the stair lights.  Due to changes in WLED, code changes were necessary for the automations.  **You will only need one of these files**.  If you are running Home Assistant core version 2021.12 or later, please use the stair_lights_ha_2021_12.yaml file.  If your version of Home Assistant is older than 2021.12, then use the stair_lights_old.yaml file.

Unless you are using the package version, **it is highly recommmended that you first create the helper input_boolean and timer entities before adding the automations** (see those folders for more details).  The package version includes the helpers along with the automations all in one file.

If you are using a split configuration in Home Assistant and have created an !include folder for your various automation yaml files in your main configuration.yaml, you can simply download the appropriate .yaml file from this folder directly into your Home Assistant automations folder *(you can change the name of the yaml file if desired to drop either the `_ha_2021_12` or the `_old` portion if desired so that your file name is just `stair_lights.yaml`... or any other name you desire)*.  If you have kept the same names for your ESPHome binary sensor entities (stair_top_motion and stair_bottom_motion) and the WLED entity (light.stair_lights), then you don't need to do anything else.  Simply reload automations from the developer tools.

If you are using a single configuration.yaml file, then some work is needed.  The contents of the appropriate automation .yaml file must be copied into your configuration.yaml file under the 
```
automation:
```
section and **each line must be indented by exactly two spaces**.  If you are using a single configuration.yaml file, or are not comfortable editing yaml files, it is recommended that you use the package version, or create the automations using the Home Assistant UI Editor, as I cover in the following video: [Recreate a YAML automation using the Home Assistant Automation Editor](https://youtu.be/F3YjWCs7Czc).  This video actually walks you through creating both the helpers and automations for the stair lighting system using the UI editor instead of editing yaml files.

### If your lights are 'reversed' when activated
As long as your 'top sensor' is at the top of the stairs and the 'bottom sensor' is at the bottom, the automation should work as is.  However, if you find that the light direction is reversed from what you want, it is an easy fix.

If you are using the newer file (for 2022.12 and later) simply edit the automations for 'Top Motion Lights On' and 'Bottom Motion Lights On'.  Locate the service call for `switch.turn_on` or `switch.turn_off` with an entity of `switch.stairs_reverse' and set the '.turn_on' or '.turn_off' to the opposite value.  This will reverse the direction of the lights when the motion sensor detects motion.

For the older version of the automation (_old), locate the same automations and look for the `reverse` action and toggle to either `true` or `false` to change the dirction.

### Changing the speed, color, brightness or effect
You can also adjust the speed, color, brightness and/or effect of the lights by editing these same sections of the automations.  To change brightness, add a `brightness:` property under the light.turn_on action and set it to a value between 0-255.  In lieu of a brightness setting, the brightness as last used or set via the WLED app will be used.

