# turn-on-motor-according-to-LDR
# abstract
this project include the ldr which will turn on the motor.
for implementing this project, we used the arduino uno, light dependent resistor, dc motor (direct current motor) and some other hardware devices.
Motor will run according to the intensity of light falls to the Light dependent resistor (LDR)
 LDR A light-dependent resistor whose resistance is inversely proportional to the intensity of light is often used as a sensor in electronic projects that involve the use of light.
The purpose of this project is to turn on the motor depending on the light intensity falling on the light dependent resistor (LDR) 
The motor is an electromechanical device that converts mechanical 
Energy into electricity energy.  This mechanical energy is used for
rotate  the  pump  impeller,  fan  or  blower,  drive  the  compressor,  lifting  materials, etc.. 
motors  are also used  in  the  home  (mixer,  electric  drill,  fan)  and  in  the industry
The circuit uses a small LDR, which is sensitive to the intensity of light. Voltages generated from the LDR are compared using an internal ADC of Arduino Uno, which turns on as light intensity goes above a certain voltage threshold. This voltage has already been calibrated for specific positions of the hand with respect to the LDR.
In this project three variations in speeds are considered: stop, medium and high. Readings from the LDR

   # Problem statement
In our days we need to use an electrical component in safety way that’s why wireless is needed in every place.
Like this project could be very useful in applications where one tries to control the movement of motor using wireless channel and to control the speed system which may be used where we need actuation with respect to different intensities of light.
Motor will be controlled in easy way without any risk.
# Block diagram
LIGHT		LDR		ARDUINO		MOTOR
When light dependent resistor supplied there is no change on the motor until the light intensity decrease on the LDR.
Light dependent resistor whose resistance is increased when light falls on it, when light dependent resistor is kept in dark, its resistance is low and that’s why the motor will turn off when the light falls on the light dependent resistor and the motor will turn on when the light goes off .
# Circuit diagram in fritzing
# Source code 
const int ldr=A0;//Set A0(Analog Input) for LDR.
const int motor =3;
void setup() {
Serial.begin(9600);
pinMode(3,OUTPUT);
pinMode(ldr,INPUT);
}

void loop() {
int ldrStatus=analogRead(ldr);
if(ldrStatus<=20)
{
  digitalWrite(3,HIGH);//Makes the motor glow in Dark.
Serial.println("DARKNESS OVER HER;TURN ON motor");//Prints the value of LDR to Serial Monitor.
Serial.println(ldrStatus);
}
else
  {
    digitalWrite(3,LOW);//Turns the motor OFF in Light.

  }
  
    Serial.println("THERE IS SUFFICIENT LIGHT, TURN OFF motor");//Prints the value of LDR to Serial Monitor.
    Serial.println(ldrStatus);
  }


