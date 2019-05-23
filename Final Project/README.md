The Color Sorter!

The basic concept of my final project is that objects with color (in my case, skittles) are inputted into the machine, the machine detects the color of the object, and then it moves it to a box that is associated with its color. The machine involves the use of 2 servo motors, an Arduino Uno, an Adafruit motor shield, hardboard and wood.


Photos:

![](Images/Project1.png)
![](Images/Project2.jpg)

Prototype:
![](Images/Prototype.jpg)

System Diagram:
![](Images/System.jpg)

Schematics:
![](Images/Scheme.jpg)


Used Parts:

2 Servo Motors:
![](Images/Servo.jpg)

1 Arduino:
![](Images/Arduino.jpg)

1 Adafruit Motor Sheild V2:
![](Images/Adafruit.jpg)

1 APDS-9960 RGB and Gesture Sensor:
![](Images/Color.jpg)

Hardboard:
![](Images/Hardboard.jpg)

Wood:
![](Images/images.jpg)


Code:
#include <Wire.h>
#include <SparkFun_APDS9960.h>                      //initiates servos and sensor
#include <Servo.h>

Servo servoup;                                     //Assigns Servo Motors
Servo servodown;

// Global Variables
SparkFun_APDS9960 apds = SparkFun_APDS9960();
uint16_t ambient_light = 0;
uint16_t red_light = 0;                                          //Assigns Input from Sensor
uint16_t green_light = 0;
uint16_t blue_light = 0;

void setup() {
  servoup.attach(10);
  servodown.attach(9);                                        //Assigns Servo Motors
 
  // Initialize Serial port
  Serial.begin(9600);
  Serial.println();
  Serial.println(F("--------------------------------"));
  Serial.println(F("SparkFun APDS-9960 - ColorSensor"));
  Serial.println(F("--------------------------------"));
  
  // Initialize APDS-9960 (configure I2C and initial values)                      //These lines are useful for following the serial inputs when the machine is running
  if ( apds.init() ) {
    Serial.println(F("APDS-9960 initialization complete"));
  } else {
    Serial.println(F("Something went wrong during APDS-9960 init!"));
  }
  
  // Start running the APDS-9960 light sensor (no interrupts)
  if ( apds.enableLightSensor(false) ) {
    Serial.println(F("Light sensor is now running"));
  } else {
    Serial.println(F("Something went wrong during light sensor init!"));
  }
  
  // Wait for initialization and calibration to finish
  delay(500);
}

void loop() {
  
  

  servoup.write(105);
  delay(2000);                                           // Motors get skittle, move infront of sensor
  servoup.write(140);
  delay(4000);

  
  if (  !apds.readAmbientLight(ambient_light) ||
        !apds.readRedLight(red_light) ||
        !apds.readGreenLight(green_light) ||
        !apds.readBlueLight(blue_light) ) {
    Serial.println("Error reading light values");
  } else {
    Serial.print("Ambient: ");
    Serial.print(ambient_light);                               //These lines read the red, green and blue lights that are infront of the sensor
    Serial.print(" Red: ");
    Serial.print(red_light);
    Serial.print(" Green: ");
    Serial.print(green_light);
    Serial.print(" Blue: ");
    Serial.println(blue_light);
  }
  
  // Wait 1 second before next reading
  delay(1000);

  if(red_light>2065 & red_light<2305 & green_light>875 & green_light<1215 & blue_light > 952 & blue_light < 1192){
    servodown.write(160);
    delay(2000); 
    servoup.write(180);
    delay(2000);
  } else if (red_light>953 & red_light<1193 & green_light>920 & green_light<1160 & blue_light >706 & blue_light < 946){
    servodown.write(130);
    delay(2000); 
    servoup.write(180);
    delay(2000);
  } else if (red_light>854 & red_light<1094 & green_light>580 & green_light<820 & blue_light >539 & blue_light <779 ){                           //All these lines are if statements that provide thresholds for the colors. Depending on the readings, the second servo will shift to a certain position. These thresholds change depending on the lighting in the room
    servodown.write(100);
    delay(2000); 
    servoup.write(180);
    delay(2000);
  } else if (red_light>1288 & red_light<1528 & green_light>588 & green_light<828 & blue_light >630 & blue_light < 870){
    servodown.write(80);
    delay(2000); 
    servoup.write(180);
    delay(2000);
  } else if (red_light>2100 & red_light<2805 & green_light>1400 & green_light<1714 & blue_light >1200 & blue_light < 1624){
    servodown.write(55);
    delay(2000); 
    servoup.write(180);
    delay(2000);
  }
}


