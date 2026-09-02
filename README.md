# RTOS Environmental Monitor - STM32F411

Multi-threaded environmental monitoring firmware built on FreeRTOS for the STM32F411 Black Pill.

## Features
- 4 concurrent RTOS tasks with priority-based scheduling
- Safe Inter-Task Communication using FreeRTOS Queues
- Shared I2C bus protection using Mutexes
- Stack overflow protection hooks

## Hardware
- STM32F411CEU6 (Black Pill)
- ST-Link V2 programmer
- I2C bus ready for BME280/MPU6050 sensor integration

## Status
- RTOS architecture complete  
- Physical sensor integration (v2.0)

