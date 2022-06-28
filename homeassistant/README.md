# Home Assistant Files

These folders contain all the necessary files for the motion-activated stair lighting system.  However, which files you need will depend on how you have Home Assistant configured and your comfort level with YAML files.

1. If you'd prefer not to mess with YAML at all, then I have a YouTube video [Recreate a YAML automation using the Home Assistant Automation Editor](https://youtu.be/F3YjWCs7Czc) that will walk you through the steps to create the necessary automations and helpers for the stair lights using the Home Assistant UI editor.  You will still need to create a couple of sections in your ESPHome code for the motion detectors (see the ESPHome folder for details), but that is the only YAML you will have to write (and you can just copy/paste that from the code provided).

2. The next best option is to use the package.  With packages, you can just copy/import the entire package YAML file into your Home Assistant packages location.  You won't need to edit anything unless you changed the name of your ESPHome (motion detectors) entities or your WLED (light) entity.  See the 'Packages' folder for more information on using the package version.

3. Finally, the individual automation, input boolean and timer files are primarily meant for use if you have Home Assistant setup in a split configuration structure (e.g. you have separate yaml files for timers, input booleans, automations, etc. and these are !included in your primary configuration.yaml file).  It is possible to use the provided yaml in your main configuration.yaml file, but care and editing will be required to assure yaml spacing and indentation is correct.

Again, if you do not have experience and are not comfortable editing yaml configuration files, I recommend that you use the first method detailed in the video.  In that case, the only code you need in these folders is the 'binary_sensor' and 'switch' sections of the ESPHome files.
