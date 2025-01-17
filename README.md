# Marlin for Artillery Hornet

For original README.md please visit [MarilnFirmware/Mariln](https://github.com/MarlinFirmware/Marlin).


## Info

- Board: Artillery Ruby (STM32F401RC)
- Pins: [pins_ARTILLERY_RUBY.h](./Marlin/src/pins/stm32f4/pins_ARTILLERY_RUBY.h)


## Hints, tips and tricks

- Be sure to calibrate printer settings that are stored in the EEPROM after a new firmware flash (menu `Store Settings` or `M500`), e.g.:
    - X / Y / Z / **E** steps/mm
    - Probe X / Y / **Z** offset
    - Bed mesh
    - Linear advance K value
- If the probe doesn't land exactly on the X/Y center while homing Z (with the correct X/Y probe offsets set), remember that the physical bed size is larger than the print area and may not be centered precisely.
    

## Configuration

### [Configuration.h](./Marlin/Configuration.h)

#### BLTouch
- `//#define Z_MIN_PROBE_USES_Z_MIN_ENDSTOP_PIN`
- `#define USE_PROBE_FOR_Z_HOMING`
- `#define Z_MIN_PROBE_PIN PC2` (`PC2` is the same pin as `Z_MAX_PIN`)
- `#define BLTOUCH`
- `#define NOZZLE_TO_PROBE_OFFSET { -24, -22, -1.39 }` - Offset for [Custom head with 5015 fans](https://www.thingiverse.com/thing:5382834)
- `#define AUTO_BED_LEVELING_BILINEAR`
- `//#define MESH_BED_LEVELING`
- `#define Z_SAFE_HOMING`
- `#define XY_PROBE_FEEDRATE (150*60)`
- `#define Z_PROBE_FEEDRATE_FAST (10*60)`
- `#define Z_CLEARANCE_BETWEEN_PROBES 3`
- `#define Z_CLEARANCE_MULTI_PROBE 3`
- `#define GRID_MAX_POINTS_X 5`

#### Linear advance

- `#define LIN_ADVANCE`
- `#define ADVANCE_K 0.94`

#### Other

- `#define HOMING_FEEDRATE_MM_M { (100*60), (100*60), (30*60) }`
- `#define DEFAULT_AXIS_STEPS_PER_UNIT { 80, 80, 400, 429 }`

### [Configuration_adv.h](./Marlin/Configuration_adv.h)

#### BLTouch

- `#define PROBE_OFFSET_WIZARD`
- `#define BABYSTEP_ZPROBE_OFFSET`
- `#define BLTOUCH_DELAY 300`
- `#define BLTOUCH_HS_MODE true`
- `#define PROBING_MARGIN_LEFT 50`
- `#define PROBING_MARGIN_RIGHT 50`
- `#define PROBING_MARGIN_FRONT 50`
- `#define PROBING_MARGIN_BACK 50`

#### OctoPrint

- `#define HOST_ACTION_COMMANDS`
- `#define HOST_PROMPT_SUPPORT`
- `#define HOST_STATUS_NOTIFICATIONS`

#### Custom Menu

- `#define CUSTOM_MENU_MAIN`


## License

[GPL license](/LICENSE)
