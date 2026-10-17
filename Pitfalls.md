# 1. The port of CH341 can't be recognized by Arduini IDE
The port wasn't recognized by Arduino IDE when I was choosing the Target Configuration
![Nano_Not_Recognized](/images/Nano_Not_Recognized.png)
SO many videos and blogs I found and summarized some tips to solve this problem. By the way, you must follow the steps to investigate errors:
- **Hardware Devices**: Check whether there are problems with the USB cable, development board, and other hardware.You can refer to this vedio:[https://www.bilibili.com/video/BV1Ab4y1z7om/?spm_id_from=333.337.search-card.all.click]
- **Device Driver**: Check whether the driver exists in your computer. You can refer to this blogs to check it, including some Linux orders. But if you are Linux, the driver is ofen in it and no mater how old it is. I didn't changed it becasue not very valuable.[https://blog.csdn.net/qq_50972633/article/details/132795565]
![driver_exists](/images/driver_exists.png)
- **Occupied**: Check whether there are other programs are occupying your ports. You can refer to this blog. That is the key of my problem and I finally sloved it.[https://blog.csdn.net/qq_27865227/article/details/125538516]
![Nano_Port_Solved1](/images/Nano_Port_Solved1.png)
When you final sloved it, your screen will look like this:
![Nano_Port_Solved2](/images/Nano_Port_Solved2.png)

# 2. Can't use "Auto Format"
The format was messy when I wrote code. I wanted to use "Auto Format" to make it clean but some bugs were appeared.
![AutoFormat_Failed](/images/AutoFormat_Failed.png)
I searched for many videos and blogs in CSDN but usless. Finally found it in official forum.[https://forum.arduino.cc/t/auto-format-goes-bonkers-ide-1-8-19/1397586]
As the official said, it can be solved by re-downloading. Here is the official web if you need to download it also:[https://www.arduino.cc/en/software/]
![Official_ArduinoIDE](/images/Official_ArduinoIDE.png)

# 3. sketch doesn't upload
My right sketch doesn't upload when I finished it. 
![Upload_Failed](/images/Upload_Failed.png)
Followed the official web's suggestions and I changed the board in **Old Bootloader** in my IDE and finally successed. If you have the same problem, please check whether the board and port are right. By the way, if you are buying board in 3rd places, check this is always right.
When you final sloved it, your screen will look like this:
![Old_Bootloader](/images/Old_Bootloader.png)