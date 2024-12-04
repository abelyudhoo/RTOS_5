# STM32 FreeRTOS LED Control Example

This repository contains a simple example of an **STM32** application using **FreeRTOS** to control multiple LEDs. The project demonstrates multitasking and synchronization in a real-time embedded system.

## Features
- **Multitasking**: Implements three tasks using FreeRTOS:
  - `defaultTask`: Placeholder for future functionalities.
  - `ledmerahTask`: Controls the red LED with a specific pattern.
  - `ledhijauTask`: Controls the green LED with a different pattern.
- **GPIO Control**: Uses STM32 HAL library to toggle GPIO pins corresponding to the LEDs.
- **Data Access Example**: A shared function (`accessData`) showcases basic synchronization.

## Project Structure
```
.
├── main.c             # Main application file
├── README.md          # Project documentation
├── CMSIS/             # CMSIS files for RTOS support
├── Drivers/           # STM32 HAL drivers
└── FreeRTOS/          # FreeRTOS kernel files
```

## Hardware Requirements
- **STM32 Microcontroller**: Designed for STM32 boards with GPIO pins configured for LEDs.
- **LED Connections**:
  - **Red LED**: Connected to GPIO pin `merah_Pin` on port `merah_GPIO_Port`.
  - **Green LED**: Connected to GPIO pin `hijau_Pin` on port `hijau_GPIO_Port`.
  - **Blue LED (optional)**: Connected to GPIO pin `biru_Pin` on port `biru_GPIO_Port`.

## Software Requirements
- **STM32CubeIDE**: Used to develop, compile, and debug the firmware.
- **FreeRTOS**: Preconfigured in the project for multitasking.
- **HAL Library**: Provides hardware abstraction for STM32 peripherals.

## How It Works
1. **Initialization**:
   - GPIO and system clock are configured during the initialization phase.
   - FreeRTOS tasks are created for controlling LEDs.

2. **Tasks**:
   - **`defaultTask`**: Does nothing (`osDelay(1)` in a loop).
   - **`ledmerahTask`**:
     - Turns on the red LED.
     - Calls the `accessData` function to perform a mock data access operation.
     - Turns off the red LED after a delay.
   - **`ledhijauTask`**:
     - Turns on the green LED.
     - Calls the `accessData` function.
     - Turns off the green LED after a delay.

3. **Shared Function**:
   - `accessData`: Demonstrates toggling the blue LED with a delay, simulating a shared resource operation.

4. **Timing**:
   - Tasks use `osDelay` to add delays between LED toggling operations.

## How to Build and Run
1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/stm32-led-control.git
   cd stm32-led-control
   ```
2. Open the project in **STM32CubeIDE**.
3. Build the project.
4. Flash the firmware onto the STM32 board.
5. Observe the LEDs toggling in their respective patterns.

## Customization
- Modify GPIO pin configurations in `MX_GPIO_Init()` if your hardware setup is different.
- Adjust task priorities and delays as needed for your application.
- Expand the `defaultTask` or add more tasks for additional functionality.
