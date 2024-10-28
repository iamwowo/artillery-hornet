# Marlin for Artillery Hornet

For original README.md please visit [MarilnFirmware/Mariln](https://github.com/MarlinFirmware/Marlin).

## Info

- Board: Artillery Ruby (STM32F401RC)
- Pins: [pins_ARTILLERY_RUBY.h](./Marlin/src/pins/stm32f4/pins_ARTILLERY_RUBY.h)

## Changes

### [Configuration.h](./Marlin/Configuration.h)

#### BLTouch
- `//#define Z_MIN_PROBE_USES_Z_MIN_ENDSTOP_PIN`
- `#define USE_PROBE_FOR_Z_HOMING`
- `#define Z_MIN_PROBE_PIN PC2` - `PC2` is the same pin as for `Z_MAX_PIN`
- `#define BLTOUCH`
- `#define NOZZLE_TO_PROBE_OFFSET { -24, -22, 0 }` - Offset for [Custom head with 5015 fans](https://www.thingiverse.com/thing:5382834)
- `#define AUTO_BED_LEVELING_BILINEAR`
- `//#define MESH_BED_LEVELING`
- `#define Z_SAFE_HOMING`
- `#define XY_PROBE_FEEDRATE (200*60)`
- `#define Z_PROBE_FEEDRATE_FAST (20*60)`
- `#define MULTIPLE_PROBING 2`
- `#define GRID_MAX_POINTS_X 4`

#### Other
- `#define DEFAULT_AXIS_STEPS_PER_UNIT   { 80, 80, 400, 408 }` - My E-Steps


### [Configuration_adv.h](./Marlin/Configuration_adv.h)

#### BLTouch

- `#define PROBE_OFFSET_WIZARD`
- `#define BABYSTEP_ZPROBE_OFFSET`
- `#define PROBING_MARGIN_LEFT 40`
- `#define PROBING_MARGIN_RIGHT 50`
- `#define PROBING_MARGIN_FRONT 50`
- `#define PROBING_MARGIN_BACK 40`

#### OctoPrint

- `#define HOST_ACTION_COMMANDS`


#### Custom Menu

- `#define CUSTOM_MENU_CONFIG`
- `#define CONFIG_MENU_ITEM_1_DESC "Boot Mode (M997)"`
- `#define CONFIG_MENU_ITEM_1_GCODE "M997"`


## License

[GPL license](/LICENSE)
