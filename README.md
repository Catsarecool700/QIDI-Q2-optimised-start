# QIDI-Q2-optimised-start

# AFTER CHANGING PRINTER.CFG MAKE SURE TO RUN Z OFFSET CALIBRATION, INPUT SHAPER CALIBRATION, Z TILT ADJUST AND A FULL BED MESH BEFORE USING YOUR PRINTER

# Changes to gcode_macro.cfg 
Removed CUT_FILAMENT_1 call from the PRINT_START macro as well as many pointless moves and homing calls (takes print prep time from ~6 minutes to ~3 minutes depending on bed mesh size and nozzle temp)

Added ADAPTIVE=1 to BED_MESH_CALIBRATE in both M4029 and _G29

Added [SCREW_TILT_ADJUST], [NOZZLE_WIPE], [DO_Z_TILT_ADJUST] and [BED_MESH] macros


# Changes to Printer.cfg
Added MCU tempreture monitoring using [temperature_sensor SOC] sensor_type: temperature_host

Removed #[include KAMP_Settings.cfg]

Commented out both [output_pin beeper] and [output_pin Polar_cooler] as I dont like the beeper and the polar cooler is seemingly a upcoming product and not yet avalible

Adjusted [idle_timeout] from 13 hours to 30 minutes

Replace [bed_screws] with [screws_tilt_adjust] and added screw4_name: rear last screw

# Additions to fluidd 
Names printer Q2

Adds all macros to folders and lables them properly 

Adds ASA and PLA preheat options 

Adjusts date to month, day, year and time to 12HR

Disables require confirm on Emergency Stop 

Enables full display
