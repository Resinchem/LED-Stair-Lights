# Input Booleans
**If you are using the package version, this is not needed, as the input boolean is included in the package**.  However, if you are using a split configuration or still have everything in your primary configuration.yaml file, you will need to add this timer.

For a split configuration, simply add the contents to your input_booleans.yaml file (or whatever file you are using for input booleans).

If you are using a single configuration.yaml file, add the contents of this file under input_boolean section (if you do not have this section, add it) and ***indent each line two spaces*** as follows:
```
input_boolean:
  stair_auto_leds:
    name: Stair Auto LEDs
    initial: on
```
