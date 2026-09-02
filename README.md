# RTOS Environmental Monitor (STM32F411)

A multi-threaded environmental monitoring firmware built on FreeRTOS for the STM32F411 Black Pill. This project demonstrates safe inter-task communication, shared hardware resource management, and fault-tolerant embedded design.

---

## Key Features

- **Multi-tasking Architecture:** 4 concurrent tasks with priority-based preemptive scheduling.
- **Safe Data Sharing:** FreeRTOS Queues prevent race conditions between tasks.
- **Hardware Protection:** Mutex locks prevent I2C bus collisions between sensor and display tasks.
- **Memory Safety:** Stack overflow hooks catch fatal errors before system corruption.
- **Fault Tolerance:** Simulated I2C timeouts with graceful error recovery.

---

## RTOS Task Architecture

- **Sensor Task (Priority 4, 500ms):** Reads I2C sensor data. Uses Mutex to protect the I2C bus.
- **Comms Task (Priority 3, 1000ms):** Sends UART telemetry to PC. Receives data via Queue.
- **Processing Task (Priority 2, On-demand):** Applies moving-average filter. Receives raw data via Queue.
- **Display Task (Priority 1, 2000ms):** Updates OLED screen. Uses Mutex to protect the I2C bus.

---

## Tech Stack

- **Hardware:** STM32F411CEU6 (Black Pill), ST-Link V2
- **IDE:** STM32CubeIDE
- **RTOS:** FreeRTOS v10.5 (CMSIS-RTOS V2 API)
- **Language:** C11