**we are going to run servo moter,brushless motors and stepper moter with Arduino**

* *servo-motor-using-Arduino* 
![servomoter](https://user-images.githubusercontent.com/81494917/180804739-77ed814e-c38e-44e1-bc2b-2db3f388fcf0.jpeg)
* Arduino Board.
* servo moter
* the black wire on the ground.
* red wire 5v.
* the third wire A1

**CODE**

#include <Servo.h>

int pos=0;

Servo servo1; 

void setup() {

  servo1.attach(9);  
  
  servo1.write(180); 
  
}

void loop() {

  for (pos = 0; pos <= 90; pos += 1) { 
  
      delay(10);                
  }
  
  for (pos = 90; pos >= 0; pos -= 1) { 
  
      delay(10);  
      
  }
  
}


https://user-images.githubusercontent.com/81494917/180806903-67314d0c-cfa0-4cf2-8594-d4fd32ce6c82.mp4

* *stepper-motor-using-Arduino*

![Terrific Tumelo (1)](https://user-images.githubusercontent.com/81494917/180808112-97b9f93a-3143-4c0d-8d9b-e9a6c10b39f7.png)

* Arduino Board.
* breadboard.
* Stepper moter


**CODE**

#include <Stepper.h>

const int stepsPerRevolution = 200;  // change this to fit the number of steps per revolution
// for your motor



// initialize the stepper library on pins 8 through 11:

Stepper myStepper(stepsPerRevolution, 8, 9, 10, 11);


int stepCount = 0;  // number of steps the motor has taken

void setup() {

  // nothing to do inside the setup
}

void loop() {

  // read the sensor value:
  
  int sensorReading = analogRead(A0);
  
  // map it to a range from 0 to 100:
  
  int motorSpeed = map(sensorReading, 0, 1023, 0, 100);
  
  // set the motor speed:
  
  if (motorSpeed > 0) {
  
    myStepper.setSpeed(motorSpeed);
    
    // step 1/100 of a revolution:
    
    myStepper.step(stepsPerRevolution / 100);
    
  }
}









* * DC brushless-motor-using-Arduino*


![photo1658743725](https://user-images.githubusercontent.com/81494917/180814716-07c8cda1-60e0-4fc6-8f05-a7b947a8a95b.jpeg)

* Arduino Board.
* breadboard.
* DC brushless moter.
* Resistor.
* Diode.
* NPN Transistor


int brightness = 0;

void setup()
{
  pinMode(9, OUTPUT);
}

void loop()
{

 
 
 for (brightness = 0; brightness <= 255; brightness += 5) {
  
  
  
  analogWrite(9, brightness);
    
    delay(30); // Wait for 30 millisecond(s)
    
  }
 
 
 
 
 

   for (brightness = 255; brightness >= 0; brightness -= 5) { 
   
   
    analogWrite(9, brightness);
    
    
    delay(30); // Wait for 30 millisecond(s)
  }
}
