# Smart Device Management System

**Course:** EL 162 / 234 – Object Oriented Programming
**Assignment:** OOP Mini Project
**Instructor:** Dr. Matthew Cobbinah

## Project Overview

This project simulates a software system used by a technology company to
manage smart devices in a smart home. Every device shares common
information — a name, a device ID, and a power status — but different
device types (security cameras, smart lights, temperature sensors) have
their own unique capabilities.

The program demonstrates core object-oriented programming concepts:

- Variables and data types
- Input and output
- Conditional statements and loops
- Functions and methods
- Classes and objects
- Constructors (`__init__`)
- Inheritance and the use of `super()`
- Encapsulation, using private attributes with `@property` getters/setters

## Class Design

### `SmartDevice` (Parent Class)
- **Private attributes:** `__device_id`, `__power_status`
- **Public attribute:** `name`
- **Methods:** `turn_on()`, `turn_off()`, `display_info()`
- `device_id` is validated so it can never be set to an empty value.
  `power_status` can only be changed through `turn_on()` / `turn_off()`,
  never assigned directly — this protects the integrity of the device
  state as required by the project scenario.

### `SecurityCamera` (Child of `SmartDevice`)
- Additional attribute: `recording_status`
- Additional methods: `start_recording()`, `stop_recording()`

### `SmartLight` (Child of `SmartDevice`)
- Additional attribute: `brightness` (validated to stay between 0 and 100)
- Additional methods: `increase_brightness()`, `decrease_brightness()`

### `TemperatureSensor` (Child of `SmartDevice`)
- Additional attribute: `temperature`
- Additional method: `read_temperature()`

Each child class calls `super().__init__(...)` in its constructor to
properly initialize the attributes inherited from `SmartDevice`.

## How to Run the Program

1. Make sure you have **Python 3** installed.
2. Clone this repository:
   ```
   git clone https://github.com/<your-username>/smart-device-management-system.git
   cd smart-device-management-system
   ```
3. Run the program:
   ```
   python3 smart_device_management.py
   ```
4. On startup, one `TemperatureSensor`, one `SmartLight`, and one
   `SecurityCamera` are created automatically. You'll then see a menu:
   ```
   1. Display Device Information
   2. Turn Device On
   3. Turn Device Off
   4. Read Temperature
   5. Adjust Brightness
   6. Start Recording
   7. Exit
   ```
   Enter the number of the option you want, and follow the prompts
   (such as choosing which device to act on).

## File Structure

```
smart-device-management-system/
├── smart_device_management.py   # Main program (all classes + menu)
└── README.md                    # Project documentation
```

## Author

<Your Name Here>
