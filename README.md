# STM32F103C8T6 - LED Blink (STM32 HAL)

This is a sample project that blinks an LED on the Blue Pill board (STM32F103C9T6) using STM32 HAL (Hardware Abstraction Layer), generated with STM32VubeMX and built with STM32VubeIDE. 

# Folder Structure 
``` bash
STM32F103C8T6-LED-blink/
    Core/
        Src/ # main.c and other source files
	Inc/
    Drivers/
	CMSIS/ # ARM Cortex headers
	STM32F1xx_HAL_Driver/
    .project # CubeIDE project files
    .cproject
````

# Tools and Environment 
* **MCU**: STM32F103C8T6 (Blue Pill)
* **IDE**: STM32CubeIDE
* **Code Generation**: STM32CubeMX (integrated in CubeIDE)
* **Library**: STM32 HAL
* **Porgrammer**: ST-Link v2

# How to build and flash 
* **Open the project**: open STM32CubeIDE -> 'File > Open Project from File System' > select the repo folder
* **Build the project**: Click the hammer icon or right-click the Project > Build
* **Flash to board**: connect to your Blue Pill via ST-Link > select your debug configuration > click the debug icon or 'Run'

# Behavior
* The LED connected to **PC13** will blink every 500ms
* The delay is created use 'HAL_Delay()' inside the main loop

``` C 
while (1) {
    HAL_GPIO_TogglePin(GPIOC, GPIO_PIN_13);
    HAL_Delay(500);
}
```

# Notes 
* PC13 is active-low on most Blue Pill boards (LED turns ON when pin is LOW)
* Make sure your board is genuine or has working crystal (common Blue Pill issue)
* HAL drivers simplify GPIO and peripheral handling, makinf this a good entry-level project

# Future Improvements 
* Add support for EXTI (External Interrupts)
* Add button-controlled blinking
* Convert to FreeRTOS task
* Port to LL (Low-Layer) drivers for more control

# Author
Chheng Lydiya

Student at Insgtitute of Technology Cambodia

GitHub: https://github.com/c-lydia

# Contributing 
This is just a learning repo, but if you have suggestions or ideas, feel free to open an issue. 
