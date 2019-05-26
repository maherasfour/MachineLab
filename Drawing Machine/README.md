Circle Drawer!

This simple machine allows the user to create variable circular designs. You can even get creative and make a maze!

![](Images/dm1.png)
![](Images/dm2.png)

Parts:
Stepper Motor - 
Servo Motor - 
Adafruit Motor Shield V2 - 
Arduino Uno - 
Prototyping Shield - 
3 Push Buttons - 
Wood - 
Wooden Sticks - 
Wooden Clip - 
Board Marker - 
Metal Wire

How it Works:

As seen from the photo above, there are two things at play here. First, there’s the servo motor that moves the marker left or right. Second, there’s the stepper motor that rotates the bottom platform with the paper. The movement of these motors depend on the push buttons that are labelled in the photo. One button makes the bottom platform rotate. The other two control the servo motor, moving them left and right. The motors are connected to external power supplies. The buttons manage the motors through the Arduino and Motor shield, and they are connected to them through a prototyping shield.

How it was Made:

(Have a look at the photo) First, the wooden base was established. Next, the two wooden stands were screwed into the base. The pivot that held the marker was constructed by drilling a hole into both the horizontal piece of wood and the vertical one. Then, a nut was hammered into the horizontal piece and a screw was screwed through the horizontal piece and the vertical one, but not too tight. This allowed for the pivot to be held straight, but at the same time it was loose enough to be moved back and forth. After that, a small hole was drilled into the horizontal piece at the opposite end to fit a thin wooden stick through. This wooden stick had a clip and marker attached to it. Then, the servo motor was drilled into the other wooden vertical piece. The stepper motor was attached to the base with hot glue. The top base for the paper is made of acrylic and was also super glued to the stepper motor. After everything was set in place, the electronics came in. The three push buttons were soldered onto a prototyping shield with resistors and connected to the Arduino. The motors were attached to the an Adafruit Motor Shield V2, which was also connected to the Arduino. The code was simple; if any current is detected in the circuits containing the pushbuttons (when the buttons are pressed), then the corresponding movement would occur (left, right or rotate). Finally, the code was uploaded to the Arduino.

Improvements:

If two buttons are pressed at the same time, the machine will only conduct one motion, and this has to do with the ordering of the code. This could be fixed by reconstructing the code in a better manner. Also, a servo motor could be added to the placed of the marker, so one does not have to manually remove the marker after drawing is finished. Lastly, one button could be added to move the stepper motor in the opposite direction.
