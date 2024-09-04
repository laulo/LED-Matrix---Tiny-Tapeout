<!---

This file is used to generate your project datasheet. Please fill in the information below and delete any unused
sections.

You can also include images in this folder and reference them in the markdown. Each image must be less than
512 kb in size, and the combined size of all images must be less than 1 MB.
-->

## How it works

SPI (Serial Peripheral Interface): The SPI interface is responsible for transmitting data between the FPGA and the MAX7219/7221 LED driver. This component sends instructions and bitmap data—essentially the visual patterns—to the MAX7219/7221, which then controls the individual LEDs on the matrix. The SPI ensures that data is sent in a synchronized manner, allowing the LED matrix to display the desired images and animations.

ROM (Read-Only Memory): The ROM stores the bitmap data that defines what will be displayed on the LED matrix. Each bitmap corresponds to a specific pattern, such as the beaver logo or the letters "BWSI." When the system is running, the controller fetches these bitmaps from the ROM and passes them to the SPI, which then sends them to the MAX7219/7221 for display.

Controller: The controller acts as the brain of the project, coordinating the operations between the SPI and ROM. It determines which bitmap to display at any given time, retrieves the corresponding data from the ROM, and instructs the SPI to send this data to the MAX7219/7221. The controller manages the timing and sequence of the displays, ensuring smooth transitions between different images on the LED matrix.

## How to test

Set Up the FPGA Development Board:
  1. Power the FPGA: Ensure your FPGA development board is powered and properly connected to your computer via USB or other power sources.
  2. Load the Design: Compile and load your Verilog design (including the LED matrix controller logic) onto the FPGA using your preferred synthesis tool
  3. Configure the I/O Pins: Map the appropriate FPGA I/O pins to the signals that will interface with the LED matrix and other hardware components.

Prepare the Breadboard:
  1. Power Rails: Connect the power (5V) and ground rails on the breadboard to the corresponding pins on the FPGA and battery.
  2. Connect the LED Matrix: Place the 32x8 LED matrix on the breadboard and connect it to the FPGA via the MAX7219/7221 controller. Ensure the connections include:
    - SPI Interface: Connect the MOSI, CLK, and CS pins of the MAX7219/7221 to the designated SPI pins on the FPGA.
    - Power and Ground: Connect the VCC and GND pins of the MAX7219/7221 to the breadboard's power and ground rails.
     
Power the Setup:
  1. Battery Connection: Attach the 5V battery to the breadboard’s power rail, ensuring that it provides power to both the LED matrix and the MAX7219/7221
     controller.
  2. FPGA Power: Ensure the FPGA is properly powered and that the input/output logic levels are compatible with the 5V system.

Run the Test:
  1. Start the FPGA: After loading the design and confirming connections, initiate the FPGA operation.
  2. Observe the Output: The LED matrix should display the programmed animations (e.g., the beaver logo and "BWSI"). If the matrix does not light up as expected,
     check connections and ensure that the FPGA is correctly driving the SPI interface.

## External hardware

A 32x8 LED matrix is used to display animations, including a beaver logo and the letters "BWSI." This matrix is controlled by a MAX7219/7221 chip, which efficiently manages the individual LEDs. To power the setup, a 5V battery is used, providing the necessary energy for the matrix and controller to function properly. 

*This project is proudly sponsored by The MITRE Corporation and the MIT Lincoln Laboratory Beaver Works Summer Institute! For more information, visit https://beaverworks.ll.mit.edu/CMS/bw/bwsi*
