# STM32F411 Nucleo Timer Counter (External Clock)

![STM32F411](https://img.shields.io/badge/STM32F411-Nucleo-blue)
![TIM1](https://img.shields.io/badge/TIM1-External_Counter-green)


![DAF0E19C-A7E8-4865-9698-32470E57E577](https://github.com/user-attachments/assets/684b8c18-f251-4f7e-bcb2-075a4e63503f)



Count external pulses using TIM1's ETR input and toggle LED on overflow.

## Features
- **External Pulse Counting** via PA12 (TIM1_ETR)
- **LED Toggle** on PA5 every 6 pulses
- **84MHz System Clock** (HSI-based PLL)
- **HAL Implementation** with interrupt


## Hardware Configuration
| Component | Specification | Nucleo Reference |
|-----------|---------------|------------------|
| MCU       | STM32F411RE   | MB1136 User Manual |
| LED       | PA5           | CN10 pin 21 |
| ETR Input | PA12           | CN10 pin 29 |
| Clock     | HSI 16MHz     | Internal |

## Technical Details
### Clock Tree (RM0383)
```c
HSI (16MHz) → PLL → 84MHz SYSCLK
PLLM = 16, PLLN = 336, PLLP = 4
APB2 Prescaler = 1 → TIM1 Clock = 84MHz
