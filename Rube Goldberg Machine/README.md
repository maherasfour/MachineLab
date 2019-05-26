Rube Goldberg Machine!

![](Images/RG2.jpg)
![](Images/RG3.jpg)
![](Images/RG4.jpg)

The Rube Goldberg Machine is a machine that is designed to perform a simple task in an indirect and overcomplicated fashion. You might have seen a lot of these if you ever watched Tom and Jerry!

Parts:

Stepper Motor -
Button -
Arduino Uno -
Motor Shield -
Sharp Blade -
Wood -
Tire -
String -
Push Button


How it Works:

On the wooden stand that holds the tire with a string, there’s a stepper motor with a blade attached to it. When the button is pressed, the stepper motor starts to saw the string that holds the tire. Once cut, the tire roles down the ramp and moves towards the wooden piece in front of it. Once it hits the wooden piece in front of it, the wooden piece falls and presses a push button. The button that’s pressed closes a circuit that is connected to an LED that lights up.

How it was Built:

This project had 2 parts: building the tire stand with the saw mechanism and building the wooden piece with the push button.

Building the Tire Stand:

The tire stand (as seen in the photos above) was made by attaching a ramp to a post. The ramp was simply a large wooden piece that was elevated with wooden pieces at its bottom. The post was also simply a tall wooden piece with a frame. All were attached to each other by drilling screws. Next, 2 wooden rectangles were attached to the post to hold the circuit and the motor with the blade. The blade was attached to the motor by gluing the blade to a cardboard base, then attaching that to 2 pieces of wood that made an 80-degree angle. The motor was attached to the wooden piece with plastic straps. On the wooden piece above it were electronics (the Arduino+motor shield, the bread board, and the button that started the stepper motor). The code for the stepper motor was simple – once the button was pressed, it would rotate about 20 degrees back and forth.

Wooden Piece with the Push Button:

First, the wooden piece was made. It consisted of two square wooden pieces that were attached to each other with a hinge. It was screwed together in a manner that when the upright wooden pieced was push it would fall flat on the other piece. Then the push button was attached to the bottom piece with screws and an aluminum piece. However, the bottom piece had to be cut so that the push button can be placed at a height such that when the top piece falls it won’t break the push button, but it would also press it. The push button had a long wire soldered to it that extended to an Arduino and bread board. Connections were made such that when the button was pressed, the LED would light up.
