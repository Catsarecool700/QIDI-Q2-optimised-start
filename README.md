# QIDI-Q2-optimised-start

# AFTER CHANGING PRINTER.CFG MAKE SURE TO RUN Z OFFSET CALIBRATION, INPUT SHAPER CALIBRATION, Z TILT ADJUST AND A FULL BED MESH BEFORE USING YOUR PRINTER

# Changes to gcode_macro.cfg 
Removed CUT_FILAMENT_1 call from the PRINT_START macro (takes print prep time from ~6m:30s to ~5m:30s depending on bed mesh size and nozzle temp)

Added comments to explain what some custom macro calls in PRINT_START do

Added ADAPTIVE=1 to BED_MESH_CALIBRATE in both M4029 and G29

Plans to optimise the number of toolhead homing moves on PRINT_START

Add [screws_tilt_adjust] macro 

# Changes to Printer.cfg
Added MCU tempreture monitoring using [temperature_sensor SOC] sensor_type: temperature_host

Removed #[include KAMP_Settings.cfg]

Adjusted [controller_fan board_fan] so fan now spins at 30% speed when motors and heaters are off and turns off competely after 5 minutes of motor inactivity

Commented out both [output_pin beeper] and [output_pin Polar_cooler] as I dont like the beeper and the polar cooler is seemingly a upcoming product and not yet avalible

Adjusted [idle_timeout] from 13 hours to 30 minutes

Replace [bed_screws] with [screws_tilt_adjust] and add screw4_name: rear last screw

# Additions to fluidd 
Names printer Q2

Adds all macros to folders and lables them properly 

Adds ASA and PLA preheat options 

Adjusts date to month, day, year and time to 12HR

Disables require confirm on Emergency Stop 

Enables full display
