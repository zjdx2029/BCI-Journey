# Day 2(2026/10/15): Python pyserial Serial Communication

## 1. The relationship between Python, IDE, and Nano
- **IDE**: Used to "burn" complied C++ code into the Nano. It can also send text commands via the Serial Monitor.
- **Python**: Has a powerful ecosystem for data processing, beyond mechanical sending/receiving. Python and IDE are parallel software running on the computer.
- **Workflow**: IDE must be used first to burn the code into the board. After that, the board continuously reads sensor data and outputs it through USB.

## 2. Core Python Code Structure
```python
import serial

# Open the serial port (Replace "xxx" with your actual port, e.g., /dev/ttyUSB0 on Ubuntu)
arduino = serial.Serial("xxx")

while True:
   
   #Sending data from PC to board  (Must encode into bytes)
   arduino.write(input("Enter message to send: ").encode())

   #Reading data from board (Must decode from bytes to string)
   print(arduino.readline().decode("ASCII"))
```

## 3. Important Notes & Lessons Learned
- **Byte Encoding**: The Nano sends and receives data as **bytes**. Therefore, we need 'encode' and 'decode' to convert between machine language and human language.
- **Exclusive Port**: **The IDE Serial Monitor must be closed when Python is rececing data!** The communication port is exclusive (1-to-1), A USB port only be occupied by one program at a time.

## 4. Arduino Side Code (Echo Back)
```cpp
String str = "";
String readLine(){
    while (Serial.available()){
        str += char(Serial.read());
        delay(2);
    }
    return str;
}

void setup(){
    Serial.begin(9600); //Match baud rate with Python
}

void loop(){
    str = readLine();
    Serial.print(str); //Echo back the recevied string
}
```

## References
- Link:
 - [https://www.bilibili.com/video/BV1at4y187yf/?spm_id_from=333.1391.0.0&vd_source=3cc578b419c0a41c2b114dbae2edafd8]
 - AI Assistant (Qianwen) : Clarify the division of roles between Arduino IDE and Python in serial communication

 ## Handwritting notes:
 - ![2.1](/images/note_Day2_1.jpg)
 - ![2.1](/images/note_Day2_2.jpg)
 - ![2.3](/images/note_Day2_3.jpg)
