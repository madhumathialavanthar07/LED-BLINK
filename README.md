# LED-BLINK
# 💡 Experiment 01 – Interfacing a Digital Output (LED) with ARM Development Board

### 🎯 **Aim**
To interface a digital output (LED) to an ARM development board and write a blink code.

---

### ⚙️ **Components Required**
- STM32CubeIDE  
- NUCLEO ARM Development Board  

---

### 🧠 **Theory**

**ARM (Advanced RISC Machine)** is a 32-bit processor architecture developed by ARM Holdings. It is widely used in embedded systems and SoC (System-on-Chip) products. Many semiconductor companies like Samsung, Atmel, and Texas Instruments license ARM architecture to design their own SoCs.
### 🧩 **What is an ARM7 Processor?**
The **ARM7 processor** is commonly used in embedded system applications. It provides a balance between the classic ARM architecture and the newer Cortex series, offering an excellent platform for both hardware and software development.
### 🔍 **LPC2148 Microcontroller**
The **LPC2148**, developed by NXP Semiconductors (Philips), is a 16/32-bit ARM7-based microcontroller featuring a wide range of peripherals.
#### **Key Features**
- 16/32-bit ARM7TDMI-S core in LQFP64 package  
- On-chip **Flash memory**: 32 KB – 512 KB  
- On-chip **SRAM**: 8 KB – 40 KB  
- **ISP/IAP** via on-chip bootloader  
- **Embedded ICE-RT** and **Real Monitor** for real-time debugging  
- **USB 2.0** full-speed device controller with 2 KB endpoint RAM  
- **10-bit ADC** (6 or 14 channels, 2.44 μs conversion time)  
- **10-bit DAC** for analog output  
- **Timers:** Two 32-bit timers, watchdog, and PWM unit  
- **RTC** with 32 kHz clock input  
- **UARTs (2x), I²C (2x)** up to 400 kbit/s  
- **5V-tolerant GPIOs**, 21 external interrupt pins  
- **Max CPU Clock:** 60 MHz using on-chip PLL (lock time 100 µs)  
- **Crystal Frequency:** 1 MHz – 25 MHz  
- **Power modes:** Idle and Power-down with peripheral clock scaling  

---

### 🧭 **Procedure**

1. Open **STM32CubeIDE**.
   <img width="1919" height="1199" alt="m1" src="https://github.com/user-attachments/assets/7e1a2928-7ff5-4279-bf7d-84c7cfe62725" />

2. Click **File → New STM32 Project**.
    <img width="1918" height="1198" alt="m2" src="https://github.com/user-attachments/assets/120ba6cd-5dce-49de-92df-e05ffff27110" />
    <img width="1920" height="1200" alt="m22" src="https://github.com/user-attachments/assets/749fbfc0-be1b-4e64-8426-9f78a3ea0e43" />

3. Select the **target microcontroller** or board and click **Next**.

   <img width="1919" height="1199" alt="m3" src="https://github.com/user-attachments/assets/fac77cb1-0366-417a-8af6-451d5c7387e2" />


4. Name the project.

    <img width="586" height="654" alt="m4" src="https://github.com/user-attachments/assets/694c3283-f9d1-40ae-a306-c29c537f2afc" />

5.The corresponding .ioc file will be generated automatically.
    <img width="1704" height="1023" alt="m5" src="https://github.com/user-attachments/assets/5f94c4f0-ac16-48fa-9488-2edefced726c" />
6. The corresponding `.ioc` file will be generated automatically.
   <img width="1702" height="1017" alt="m6" src="https://github.com/user-attachments/assets/982ddf6e-c0ef-4465-a270-e972a49ab227" />
   <img width="1706" height="1016" alt="m66" src="https://github.com/user-attachments/assets/0a89a8c7-1607-430c-a89e-ee6322a6a1a0" />
7.Save the configuration (Ctrl + S) – the base C program will be generated automatically.
    <img width="1706" height="1025" alt="m7" src="https://github.com/user-attachments/assets/0a869ce5-294a-40ee-8731-901faba5c242" />
8.Edit the generated main program as required.
     <img width="1919" height="1199" alt="m8" src="https://github.com/user-attachments/assets/7f14094d-ebf3-4b23-8030-bdf3d89b5515" />
     <img width="1919" height="1199" alt="m88" src="https://github.com/user-attachments/assets/c1d7cb24-741b-43d1-9bd4-57b7dcbf97ff" />

9. Click Project → Build All.

      <img width="958" height="242" alt="m9" src="https://github.com/user-attachments/assets/333caf3a-471b-47ab-88af-dd042030e695" />
10.Link the HEX file using the post-build process.
      <img width="1919" height="1199" alt="m10" src="https://github.com/user-attachments/assets/0ae0bdc7-1900-4021-bd27-edd4f6a5b237" />
11. Edit the generated main program as required.
       <img width="1914" height="1199" alt="m11" src="https://github.com/user-attachments/assets/1a9d4497-3108-4078-aae9-e9edc5139dc7" />

13.Click run to execute the program     
### 💻 **Program**


```c
#include "main.h"

void SystemClock_Config(void);
static void MX_GPIO_Init(void);

int main(void)
{
    HAL_Init();
    SystemClock_Config();
    MX_GPIO_Init();

    while (1)
    {
        HAL_GPIO_WritePin(GPIOA, GPIO_PIN_5, GPIO_PIN_RESET);
        HAL_Delay(1000);
        HAL_GPIO_WritePin(GPIOA, GPIO_PIN_5, GPIO_PIN_SET);
        HAL_Delay(1000);
    }
}
```
---
### OUTPUT
CASE 1: LED ON 

<img width="603" height="432" alt="led on" src="https://github.com/user-attachments/assets/f193dbac-0aa0-41a2-b389-d5bbe30770e1" />

CASE 2: LED OFF

<img width="596" height="416" alt="led off" src="https://github.com/user-attachments/assets/df0212eb-6750-426e-9f62-d8854614e79f" />


---
### RESULT
Interfacing a digital output with ARM microcontroller is executed and the results are verified.
