# FreeRTOS
===========================================================
Project Info
===========================================================
Project Name 				: HomeAutomationSystem
Kernel 						: FreeRTOS
ompiler 					: GCC
IDE 						: STM32CubeIDE V 1.10.1
Target Board 				: STM32F407VGTx based Discovery Board
===========================================================
Steps to create a FreeRTOS based project in STM32CubeIDE
===========================================================
1. Download FreeRTOS Kernel from https://www.freertos.org/a00104.html
2. Create project from STM32CubeIDE
	While creating project,
	a. Not need to intialize all the peripherals
	b. Select "Target Project Type" as STM32Cube not as "empty"
3. Add Common->ThirdParty folder inside freeRTOS workspace
4. Copy FreeRTOS folder from newly downloaded FreeRTOS Kenrel directory with selected subfolders and files
5. Delete the sysmem.c from core->src folder because memory management is taken care by FreeRTOS kernel
6. Go to FreeRTOS->Portable->Memmang and choose only one heap management file while delete the others
7. Make sure that FreeRTOS Kernel is included in build
8. Make sure all the header files are included.
	a. Go to project->settings->c/c++ build->include path-> add paths from FreeRTOS kernel folder
9. Add FreeRTOSConfig.h in src->include folder and add the path for the file.
	b. If you do not have config file already, pick a file from demo project and check the "Developer Docs" from documentation
10. Build and resolve the build issue until it works fine.
	a. Do required changes in config file
	b. from *.ioc file, system core->sys-> select priority group -> untick pendSV, systick and SWI interrupt generation from system core
	c. Select timer base(timer-6) from Sys tab
	d. Disable hooks from config file
	
