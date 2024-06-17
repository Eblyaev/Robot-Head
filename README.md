# Robot-Head
Насадка работает от подключения питания аккамулятором. Код написан ниже.
```c++
// #include <Arduino.h>
#include <TB6612_ESP32.h>


// *** Wiring connections from ESP32 to TB6612FNG Motor Controller ***


#define AIN1 13 // ESP32 Pin D13 to TB6612FNG Pin AIN1
#define BIN1 12 // ESP32 Pin D12 to TB6612FNG Pin BIN1
#define AIN2 14 // ESP32 Pin D14 to TB6612FNG Pin AIN2
#define BIN2 27 // ESP32 Pin D27 to TB6612FNG Pin BIN2
#define PWMA 26 // ESP32 Pin D26 to TB6612FNG Pin PWMA
#define PWMB 25 // ESP32 Pin D25 to TB6612FNG Pin PWMB
#define STBY 33 // ESP32 Pin D33 to TB6612FNG Pin STBY


// *** Wiring connections from TB6612FNG Motor Controller to the Motors ***


// Connect the leads from your motors, don't worry if you don't get them correct the first time
// Motor 1 should go to A01 and A02
// Motor 2 should go to B01 and B02
// If the motors are NOT turning in the right direction reverse the pins (for example the A01 and A02) pins
// If the left and right motors are reversed then swap the A01 and A02 wires to the B01 and B02 pins 


// *** Wiring connections from the Battery Pack to the ESP32 and TB6612FNG Motor Controller ***


// A 4 Cell battery pack was used to supply 6 Volts of DC current to the robot and to the ESP32
// A wire splitter was used to connect the Positive (+) side of the Battery pack to the VIN pin of the ESP32,
// and to the VM pin of the TB6612FNG Motor Controller.
// Another wire splitter was used to connect the Negative (-) side of the Battery pack to the GND pin of the ESP32,
// and to the GND pin of the TB6612FNG Motor Controller


// these constants are used to allow you to make your motor configuration
// line up with function names like forward.  Value can be 1 or -1
const int offsetA = 1;
const int offsetB = 1;

Motor motor1 = Motor(AIN1, AIN2, PWMA, offsetA, STBY,5000 ,8,1 );
Motor motor2 = Motor(BIN1, BIN2, PWMB, offsetB, STBY,5000 ,8,2 );

// Initializing motors.  The library will allow you to initialize as many
// motors as you have memory for.  If you are using functions like forward
// that take 2 motors as arguements you can either write new functions or
// call the function more than once.

void setup()
{


}


void loop()
{
     
     motor1.drive(255);       // Turn Motor 1 for 2 seconds at full speed
     //motor1.drive(-255,2000);
   
}
```
