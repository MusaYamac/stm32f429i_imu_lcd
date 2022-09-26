# stm32f429i_imu_lcd
**IMPORTANT** Do not use ioc file to configurate the touchgfx generated projects on CubeIDE. If you need to make adjustments on the touchgfx generated projects, dive into the code files.
The main.c is in ...\Core\Src. That contains the main code + the linkings to the libraries. Run and edit that file. Do not change the location of the files. 

This project has two major parts. Firstly, it reads and filters the data from IMU sensor (either mpu6050 or 9250), then it evaluates the yaw, roll and pitch angles. Secondly it'll activate the lcd screen, display an image of the sensor and print the evaluated sensor datas. It has considerable delay, which is due to the timers. I didn't activate a new timer to send sensor data to the buffer of the screen display. Instead used the ones that were activated by the touchgfx code generator. This retarded data issue can be solved by activating a new timer and assigning it as an interrupt via the c. DO NOT USE IOC FILE TO EDIT THE PROJECT. You can only edit the project on the code files. That's due to the poor integration of the touchgfx to cubeide.

Since the upload size is limited, i've excluded the "Middlewares" folder which contains the touchgfx files. You don't need that to run the code on your board anyways.


