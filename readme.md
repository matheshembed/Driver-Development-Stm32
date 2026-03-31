STM32 Bare-Metal Driver Development

This repository documents my journey of learning embedded systems by building peripheral drivers for STM32 microcontrollers from scratch using bare-metal programming.

---
## Purpose

The objective of this project is to develop a strong foundation in embedded systems by:

- Writing peripheral drivers from scratch using register-level programming
- Understanding ARM Cortex-M architecture and memory-mapped I/O
- Analyzing and configuring microcontroller subsystems using reference manuals
- Gaining practical experience in debugging and hardware validation

This work is intended to prepare for advanced topics such as RTOS and Linux device driver development.

---

## Project Structure

The repository is organized as a progression of experiments and driver development:

- `00_Concepts/`  
  Personal notes and breakdown of key embedded concepts (registers, memory map, clock system, etc.)

- `01_Hello_World/`  
  Initial project setup to understand:
  - Toolchain and build process  
  - Startup code and linker behavior  
  - Flashing and execution flow  

- `02_Clock_Config/`  
  System clock configuration experiments:
  - Configured system clock using internal (HSI) and external (HSE) oscillators  
  - Observed clock output behavior using MCO pin  
  - Explored clock tree dependencies and RCC configuration  

- `03_GPIO/`  
  GPIO programming at register level:
  - Configured GPIO pins for output (LED control)  
  - Implemented input handling using push button  
  - Verified behavior through hardware testing  

- `stm32f446xx_drivers/`  
  Ongoing implementation of reusable peripheral drivers:
  - GPIO (in progress)  
  - Future: UART, SPI, I2C, RCC  

- `Datasheets_Manuals/`  
  Reference materials used during development (STM32 datasheet, reference manual)

- `Questions_&_Answers/`  
  Collection of doubts encountered during development along with explanations and solutions

---

## Learning Approach

This project follows a strict **bare-metal methodology**:

- No use of STM32 HAL or external abstraction layers  
- Direct manipulation of peripheral registers  
- Continuous reference to official datasheets and reference manuals  
- Writing drivers incrementally to understand internal behavior  

Focus is placed on:
> **Understanding hardware behavior first**, then building abstractions on top.

---

## Experiments & Validation

All implementations are verified using real hardware:

- LED toggling used to confirm GPIO output configuration  
- Push button used for input validation  
- Clock signals observed through MCO pin  
- Debugging performed using ST-Link  
- Logic analyzer for protocol-level debugging (SPI/I2C/USART)

---

## Key Concepts Explored

- Microcontroller startup sequence  
- Memory-mapped peripheral access  
- RCC (Reset and Clock Control) configuration  
- Clock sources (HSI vs HSE) and their behavior  
- GPIO register configuration  
- Embedded C for low-level programming  

---

## Challenges Faced

- Understanding clock tree configuration and dependencies  
- Debugging issues caused by incorrect RCC settings  
- Interpreting reference manual details and register descriptions  
- Verifying behavior without  debugging tools  

---

## Key Observations

- Peripheral registers are inaccessible unless the corresponding clock is enabled in RCC  
- Incorrect clock configuration can silently break peripheral functionality  
- Hardware-level debugging requires systematic validation (not trial-and-error)  
- Datasheets and reference manuals are essential — not optional  

---

## Tools & Hardware

- **Board:** STM32 Nucleo-F446RE  
- **Core:** ARM Cortex-M4  
- **Compiler:** arm-none-eabi-gcc  
- **Debugger:** ST-Link  

**Hardware used for validation:**
- LED → Output verification  
- Push button → Input testing  
- Logic analyzer → Communication debugging  

---