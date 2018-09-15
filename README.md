# spareparts
3d models of various random electronic and mechanical components for OpenSCAD

Descrete logic for PCB
~~~scad
use <spareparts/descrete.scad>

power_jack_socket();
translate([30, 0,0]) usb_b_socket();
translate([60, 0,0]) mini_usb_socket();
translate([90, 0,0]) button();
translate([120, 0,0]) trimming_resistor(val=15);
translate([150, 0,0]) screw_terminal(count=2, center=true);
translate([180, 0,0]) GPIO_socket(count_x=8, count_y=2);
translate([230, 0,0]) pin_row(count_x=8, count_y=2, center=true);
translate([270, 0,0]) pin_row_bended(count=8, center=true);
translate([300, 0,0]) led_head();
~~~

Parametric microchips in DIP and SMD
~~~scad
use <spareparts/microchips.scad>

// L293D - DIP
chip_dip(legs=8);

// L393D - SMD
translate([10, 0, 0]) chip_smd(dim_x=3, dim_y=4.6, pins_x=0, pins_y=8, shift_y=0.2);

// PIC32 с ChipKIT Uno32
translate([20, 0, 0]) chip_smd(dim_x=10, dim_y=10, pins_x=15, pins_y=15);

// AVR с китайской ардуины
translate([40, 0, 0]) chip_smd(dim_x=6, dim_y=6, pins_x=8, pins_y=8);
~~~

Sockets and other components for panel mount (modules with "pm" postfix)
~~~scad
use <spareparts/panel-mount.scad>

on_off_btn_pm(shadow=false);
translate([40, 0, 0]) power_socket_pm(shadow=false);
translate([90, 0, 0]) power_socket_with_button_pm(on=true, skirt=false, shadow=false);
translate([150, 0, 0]) power_socket_with_button_pm(on=true, skirt=true, shadow=false);
translate([210, 0, 0]) usb_b_socket_pm(shadow=false);
~~~

Plugs and jacks for wires
~~~scad
use <spareparts/plugs_n_jacks.scad>

head_pin();
translate([20, 0, 0]) u_shape_terminal();
translate([40, 0, 0]) socket_bls(count=3);
translate([60, 0, 0]) power_plug_jack();
translate([80, 0, 0]) usb_a_plug();
translate([100, 0, 0]) usb_b_plug();
~~~

Sensors
~~~scad
use <spareparts/sensors.scad>

sonar();
translate([40, 0, 0]) ir_line_sensor();
~~~

Arduino boards and shields
~~~scad
use <spareparts/arduino.scad>

chipkit_uno32();
translate([100, 0, 0]) arduino_uno();
translate([200, 0, 0]) arduino_uno_china();
translate([300, 0, 0]) cnc_shield(drivers=true, drivers_radiator=false);
~~~

