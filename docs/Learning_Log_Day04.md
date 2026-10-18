# Day 4: Arduino Setup & Serial Communication

## 1. Data Acquisition Flowchart
*Note: Today's focus is the Lower Computer (Arduino).*
- **Upper Computer (Python)**: Monitoring & Display. Responsible for receiving, monitoring, processing, and visualizing signals.
- **Lower Computer (Arduino)**: The brige. Converts bio-signals into digital signals.
- **Hardware Sensor (AD8232)**: Raw bio-signal collection.

## 2. Code Debugging & Corrections
- **Initial Mistake**: This was my first time writting code based on the IDE tutorial. However, I didn't fully understand what the code was actually doing inside the Nano board. I mistakenly used `Serial.readline() = str` (mixing up the logic).

```cpp
String str;

void setup(){
    Serial.begina(9600);
}

void loop(){
    Serial.readLine() = str;
    Serial.println(str);
    delay(2);
}
```
- **The Root Cause**: I lacked a clear concept of the "data acquisiton" flow and was unfamiliar with the IDE commands.
- **Correct Code**: 

```cpp
void setup(){
    Serial.begin(9600);
}

void loop(){
    int sensorValue = analogRead(A0); 
    Serial.println(sensorValue);
    delay(2);
}
```

## 3. Key Concept: Analog vs. Digital & ADC
- analogRead(): Read analog signals.
- digitalRead(): Read digital signals.

**How does the Nano process Analog signals?**
The bio-signals we collect are contiously changing. The Nano board contains a hardware module called ADC (Analog-to-Digital-Converter).

When analogRead() is called, the ADC divides the voltage range into 1024 parts. Because the Nano's ADC is 10-bit ($2^{10} = 1024), the output value ranges from 0 to 1023.

## 4. Learning Reflections
- **1. Theory vs. Practice**: They are vastly different. I studied the theory for days, but still faced a blank wall when actually writting code and operating hardware. However, the blurry and neglected areas were reinforced during practice.
- **2. Debugging logs**: Encountered many issues today. Detailed records are in [Pitfalls.md] #1-#3.
- **3. AI Assistance**: Using DeepSeek is incredibly helpful for understanding knowledge.
- **4. Mindset Shift**: I used to just ask AI immediately when facing problems. Now, when I see a error, I konw how to searching GitHub, CSDN, Official fourms and other communities for answers. The process of searching, judging, practicing, and organizing gives me a much deeper understanding of my project.