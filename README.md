# Dog-Tail-Simulation

### What I've Built
-----

This code is a simulation of the tail of a robotic dog. The speed of the wagging depends on the distance calculated from the HC-SR04 ultrasonic distance sensor.

-----
### How It Works
-----
The distance is calculated by the HC-SR04 distance sensor on the basis of ultrasonic waves. It emits sound waves at a certain frequency and detects how much time it takes for the waves to return and then calculates the distance with the help of the speed of sound and the time for the wave to come back.

It then takes the distance and decides how fast the servo motor should change its orientation to simulate the wagging of the tail, if the distance is large, the wagging is slow and lazy and is fast when the distance is within a certain limit.

There is also a button which makes the dog "sit". In order to simulate that the tail stops in the middle for about 3 seconds and then starts wagging again.

-----
### Problems Occurred
-----
There was one issue that was coming while implementing the sit button.  When the wagging function is called, then the code cannot detect the press of the button as it was running in the function and not in the loop code. Even when the program returns from the function, there was only a small window where the button press would get detected before the program shifts to the function again and the press would not be detected. 

The fix to this problem was to check for the button press in the function itself too and to set a boolean variable to represent the press and to reset it at the start of the loop code.

There could be more efficient solutions to this problem but as I am a beginner in robotics, this was the easiest for me to implement in the given time period.

There weren't any more problems encountered during the making of the simulation.

-----
### How I Feel
-----
I would be happy to learn more about robotics and how it works behind all the physical parts, and I am ready to face any challenges that could occur in the making of the robotic dog and learn to fix it.

I would be grateful to be selected in the team, and this would be the biggest learning opportunity for me in the field of electronics and robotics.
