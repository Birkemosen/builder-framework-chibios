# Builder-framework-chibios
CHIBIOS build script for PlatformIO Build System

# Setup
- Create the following folder stucture under packages directory

        + framework-chibios
            + platformio 
                ldscripts

- Copy "os" folder from chibios 18.2.1 to _"framework-chibios"_
    - https://github.com/ChibiOS/ChibiOS.git
    - branch: stable_18.2.x
- Copy "chibios.py" to _"platforms/ststm32/builder/frameworks/"_
- Update packages.json

# Build Flags
By default this script compiles the Chibios/HAL only. 
To enable other features of CHIBIOS, use the following `"build_flags"`.

##### Use Chibios/NIL
 Enable the Chibios/NIL RTOS kernel. 
 _Note: Only one Kernel can be used at a time._
 `-D PIO_CHIBIOS_USE_NIL`

###### Use Chibios/RT 
 Enable the Chibios\RT RTOS kernel. 
 Only one Kernel can be used at a time.
 `-D PIO_CHIBIOS_USE_RT`

###### Use I2C Fallback driver
 Use the I2C Fallback LLD driver instead of the board specific LLD driver.
 `-D PIO_CHIBIOS_I2C_FALLBACK`

##### Enable C++ Wrappers
 Adds the Chibios CPP_Wrappers to the build
 `-D PIO_CHIBIOS_USE_CPP` 

##### Enable Floating Point Unit
 Enable FPU using softfp
 `-D PIO_CHIBIOS_USE_FPU` 

##### Change Main Stack Size 
  Change the default value (0x400) for \_\_main_stack_size__. 
  `-D USE_MAIN_STACKSIZE=<value>`
##### Change Process Stack Size
  Change the default value (0x400) for \_\_process_stack_size__. 
  `-D USE_PROCESS_STACKSIZE=<value>`
