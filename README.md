# Embedded Systems Course Material

This repository is a French-language study collection for embedded-system architecture and STM32 development. It contains a numbered lesson sequence plus two vendor reference documents. There is no firmware project or executable build in the repository.

## Recommended reading order

| Order | Document | Main subject |
| ---: | --- | --- |
| 0 | `0_arch_ES.pdf` | Embedded-system architecture and an introduction to embedded C. |
| 1 | `1_outil_developpement_ARM2.pdf` | ARM/Cortex and STM32 development tools. |
| 2 | `2_prise en main.pdf` | Getting started with Keil uVision, CMSIS/startup files, and an STM32F103RB/NUCLEO workflow. |
| 3 | `3_Manipulation des registres et des masques.pdf` | Register access, bit masks, and STM32F103 examples. |
| 4 | `4_GPIO.pdf` | General-purpose input/output configuration and use. |
| 5 | `5_Gérer le temps avec les timers.pdf` | Timing and timer peripherals. |
| 6 | `6_Gérez vos interruptions.pdf` | Interrupt handling, the NVIC, and timer-driven examples. |

Read the numbered documents from `0` through `6`; later lessons assume concepts introduced earlier.

## Reference documents

| Document | Use |
| --- | --- |
| `en.CD00171190.pdf` | STMicroelectronics RM0008 reference manual for STM32F10xxx devices (the checked-in copy identifies itself as Rev 20, December 2018). Use it for peripheral registers and device-family behavior. |
| `stm32f401re.pdf` | STM32F401xD/xE device datasheet. Use it for device features, limits, package information, and pin definitions for the F401 family. |

## Important device-family note

The lesson material uses STM32F103/F1 examples, while `stm32f401re.pdf` describes an STM32F401/F4 device. These families do not share every register layout, clock-tree detail, interrupt mapping, alternate function, electrical limit, or pinout. Do not copy an F1 register example into an F4 project without checking the reference manual and datasheet for the exact target part.

For each exercise:

1. Identify the full MCU part number and board revision.
2. Use the matching reference manual, datasheet, and errata sheet.
3. Confirm the clock source and peripheral clock before calculating delays or timer periods.
4. Confirm pin alternate functions and voltage limits before wiring hardware.
5. Check the startup code, CMSIS device package, compiler, and debugger configuration for the selected MCU.

## Suggested study workflow

1. Start with architecture and the development-tool overview.
2. Recreate the introductory project for the intended board rather than assuming the example target.
3. Practice register masks on a disposable test project.
4. Validate GPIO using a low-risk LED or logic-analyzer test.
5. Verify timer frequency mathematically and with an oscilloscope or logic analyzer.
6. Add one interrupt source at a time and inspect pending/enabled flags in the debugger.
7. Keep a short lab note containing the exact board, MCU, tool versions, clock configuration, and observed result.

## Tools

The slides introduce an ARM/STM32 workflow including Keil uVision and CMSIS. Equivalent current STM32 tools may be used, but screens and project-generation steps can differ. Always follow the documentation for the installed tool version and the selected development board.

## Source and licensing note

These PDFs include teaching and vendor material, but this repository does not state their authorship, license, or redistribution terms. Copyright remains with the respective authors and publishers. Preserve notices in the documents, use them for legitimate study, and obtain current STMicroelectronics manuals from the official source when accuracy or redistribution rights matter. No repository-level license is included.
