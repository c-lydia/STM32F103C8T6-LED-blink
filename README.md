# STM32F103C8T6-LED-blink
This explains how to use STM32F103C8T6 with STM32CubeIDE for the first STM32 project (LED Blink)

## Hardware connection
1. connect the board to the ST Link
2. connect the board to the breadboard
3. use a jumper wire to connect from Ground pin (G) on the board to the ground (-) on the breadboard
4. connect the LED, the anode (positive) to the pin A1, and the cathode (negative) to the ground (-) on the breadboard

## Coding the microcontroller
The idea is to use HAL library to toggle the pin. 

``` C 
 while (1)
  {
	  HAL_GPIO_TogglePin(GPIOA, GPIO_PIN_1);
	  HAL_Delay(1000);
  }
}
```


This function toggles the state of the GPIO pin. 
``` C 
HAL_GPIO_TogglePin(GPIOA, GPIO_PIN_1);
```
This code selects the port A as the port of the GPIO pin to toggle the state.
``` C 
GPIOA
```

And this one specifies which pin on port A to toggle. 
``` C
GPIO_PIN_1
```

This function delays the code execution by 1000 milisecond. 
``` C
HAL_Delay(1000);
```
