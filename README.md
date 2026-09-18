# IMPLEMENTATION OF GPIO INTERFACING WITH RASPBERRY PI USING PYTHON – LED, PUSH BUTTON AND SENSOR

## Aim

To interface an LED, push button, and analog sensor with Raspberry Pi using Python and observe their operation through GPIO and ADC.

# Hardware / Software Tools Required

- Raspberry Pi Pico
- LED
- Push Button
- Analog Sensor
- Resistor
- Breadboard
- Jumper Wires
- USB Cable
- Wokwi Simulator
- MicroPython

# Circuit Diagram

<img width="876" height="543" alt="Screenshot 2026-09-08 131711" src="https://github.com/user-attachments/assets/1943fb75-e670-472b-ac00-1be2e2c8af15" />


# Procedure

## Step 1: Create the Circuit

1. Open the Wokwi online simulator.
2. Add the Raspberry Pi Pico board.
3. Connect the LED to GPIO 15.
4. Connect the push button to GPIO 16.
5. Connect the analog sensor to ADC GPIO 28.
6. Connect the required power and GND connections.
7. Verify all circuit connections.

## Step 2: Configure the GPIO Pins

1. Configure GPIO 15 as an output for the LED.
2. Configure GPIO 16 as an input for the push button.
3. Configure GPIO 28 as an ADC input for the analog sensor.
4. Initially turn the LED OFF.

## Step 3: Write and Run the Program

1. Open the MicroPython editor in Wokwi.
2. Enter the Python program.
3. Configure the LED, push button, and ADC pins.
4. Run the program.
5. Continuously monitor the push button and analog sensor values.

## Step 4: Control the LED

1. Press the push button.
2. When the button is pressed, the LED turns ON.
3. Release the push button.
4. When the button is released, the LED turns OFF.
5. The LED operation is continuously controlled according to the button state.

## Step 5: Read the Analog Sensor

1. The analog sensor value is continuously read using the ADC.
2. The ADC value is displayed in the output console.
3. The ADC value is converted into voltage.
4. The corresponding voltage value is displayed in the output console.

## Step 6: Observe the Output

1. Start the Wokwi simulation.
2. Press the push button and observe the LED.
3. Release the push button and observe the LED.
4. Observe the analog sensor value in the console.
5. Observe the calculated voltage value.
6. Repeat the operation for different sensor values.

# Program

```
from machine import Pin, ADC
from time import sleep

LED = Pin(15, Pin.OUT)
BUTTON = Pin(16, Pin.IN)
adc = ADC(Pin(28))

LED.off()

while True:
    if BUTTON.value() == 1:
        print("Button pressed, LED toggle")
        LED.on()
    else:
        LED.off()

    analog_value = adc.read_u16()
    print(f"Analog value: {analog_value}")

    voltage = analog_value * (3.3 / 65535)
    print(f"Voltage: {voltage}")

    print("==========")
    sleep(0.1)
```

# OUTPUT

<img width="1920" height="1080" alt="Screenshot 2026-09-08 131631" src="https://github.com/user-attachments/assets/16e98c15-12b4-4cf4-ae1e-1612917ecc48" />



# RESULT
The GPIO interfacing of an LED, push button, and analog sensor with Raspberry Pi Pico was successfully implemented using MicroPython. 
The LED was controlled using the push button, and the analog sensor value was read using the ADC and converted into the corresponding voltage.
