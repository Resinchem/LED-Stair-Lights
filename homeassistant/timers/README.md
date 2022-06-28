# Timers

**If you are using the package version, this is not needed, as the timer is included in the package**.  However, if you are using a split configuration or still have everything in your primary configuration.yaml file, you will need to add this timer.

For a split configuration, simply add the contents to your timers.yaml file (or whatever file you are using for timers).

If you are using a single configuration.yaml file, add the contents of this file under timer section (if you do not have a timer section, add it) and ***indent the line two spaces*** as follows:
```
timer:
  stair_lights_timer:
```

If you change the name of the timer, be sure to update the automations file as well to use the different timer name.
