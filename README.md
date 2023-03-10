# Learning ESP32

Learning how to use the ESP32 DevKit.

Testing out hardware connections and using GPIO pins.

Using the Espressif Wroom 32D on a 30-pin NodeMCU board.

![pinout](./pinout.webp)

# WiFi

ESP32 supports WiFi 802.11 b/g/n at 2.4GHz.

- Data rates of up to 150 Mbps
- Adjustable transmit power up to 20.5 dBm
- Supports antenna diversity, using GPIO to control RF switch
- Exposed in the `WiFi.h` library

Station (STA) mode makes the ESP32 a client of a WiFi router.

Soft Access Point (AP) mode makes the ESP32 a router without a connection to the Internet.

- Maximum of 5 clients

Both modes allow ESP32 to act as a web server.

# Bluetooth

ESP32 has both classic Bluetooth and Bluetooth Low Energy (BLE).

- It can act as a client and a server

Classic Bluetooth can be used for:

- continuous data streaming
- wireless headsets
- file transfers
- wireless keyboards and mice
- wireless speakers

BLE can be used for:

- short bursts of data
- IoT sensors
- fitness bands
- medical monitors

# Button

The button has two terminals. The lateral pins of the button are internally connected and make up one terminal per pair. The two terminals are only connected when the button is pressed.

To detect button presses, we have to read a change in voltage.

If we connect one terminal of the button to a GPIO and another to VIN or 3X3, then the GPIO will read LOW when the button is unpressed and HIGH when the button is pressed. **Ensure that a resistor lies in the circuit to prevent a short circuit**.

If we connect one terminal of the button to a GPIO and another to ground, then the GPIO will always read LOW. To read HIGH when unpressed, we have to add another connection between VIN or 3X3 and the GPIO, **with a resistor in the circuit**. When the button is unpressed, the GPIO will read HIGH. When the button is pressed, the voltage will drain into ground and result in a LOW reading at the GPIO.
