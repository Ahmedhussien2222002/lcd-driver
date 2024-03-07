<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>ATmega32 LCD Driver</title>
</head>
<body>
  <h1>ATmega32 LCD Driver</h1>
  <p>This repository contains a driver for interfacing with Liquid Crystal Displays (LCDs) using ATmega32 microcontroller.</p>

  <h2>Features</h2>
  <ul>
    <li>Supports 16x2 LCD.</li>
    <li>Simple and intuitive API for easy integration.</li>
    <li>Customizable character display.</li>
    <li>Built-in functions for printing strings and characters.</li>
  </ul>

  <h2>Getting Started</h2>
  <ol>
    <li><strong>Hardware Setup:</strong> Connect your LCD to ATmega32 according to its datasheet. Typically, you'll need to connect power, ground, and data pins.</li>
    <li><strong>Download the Library:</strong> Download or clone this repository to your local machine.</li>
    <li><strong>Include Library in your Project:</strong> Copy the `LCD.h` , `LCD.c` , `DIO_Module.c` and `DIO_Module.h` files into your project directory.</li>
    <li><strong>Include the Header File:</strong> Include the `LCD.h` header file in your project.</li>
    <li><strong>Initialize the LCD:</strong> Initialize the LCD by calling the initialization function provided by the driver.</li>
    <li><strong>Start Using the Functions:</strong> Now, you can start using the provided functions to control the LCD. Refer to the documentation in the header file for a list of available functions and their usage.</li>
  </ol>
<h1>LCD Hardware Interface</h1>
  <p>This file simulates the idea of GUI in a software application and allows you to define which ATmega32 pins you want to connect an LCD on.</p>
  <h2>How it Works</h2>
  <ol>
    <li>Use <code>LCD_CONNECTED_PORT</code> macro to select which port of ATmega32 you will connect the LCD to.</li>
    <li>Use <code>LCD_PINS</code> macro to define how many pins you need to connect the LCD:
      <ul>
        <li><code>4</code> means that the LCD works in 4-bit mode.</li>
        <li><code>8</code> means that the LCD works in 8-bit mode.</li>
        <li>Otherwise, it will generate a warning or the LCD might not work.</li>
      </ul>
    </li>
    <li>If you want to work with 4-bit mode, use the <code>IS_CONNECTED_TO_HIGH_PINS</code> macro to define which pins you will connect the LCD to:
      <ul>
        <li><code>0</code> means that you will connect <code>D4, D5, D6, D7</code> of the LCD to the first 4 pins of the selected port in the microcontroller.</li>
        <li><code>1</code> means that you will connect <code>D4, D5, D6, D7</code> of the LCD to the last 4 pins of the selected port in the microcontroller.</li>
      </ul>
      <p>Note: If you want to work with 8-bit mode, then any value of <code>IS_CONNECTED_TO_HIGH_PINS</code> macro is not affected.</p>
    </li>
    <li>Use <code>REGISTER_SELECT_PORT</code> macro to define which port of the microcontroller you will connect the register select pin of the LCD to.</li>
    <li>Use <code>REGISTER_SELECT_PIN</code> macro to define which pin of the microcontroller you will connect the register select pin of the LCD to.</li>
    <li>Use <code>ENABLE_PORT</code> macro to define which port of the microcontroller you will connect the enable pin of the LCD to.</li>
    <li>Use <code>ENABLE_PIN</code> macro to define which pin of the microcontroller you will connect the enable pin of the LCD to.</li>
  </ol>
  <p>Note: The default configuration assumes that the LCD is connected to the last 4 pins of port A, register select pin is connected to port B pin 1, and enable pin is connected to port B pin 0.</p>
</body>
</html>
