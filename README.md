# smartbin
Smartbin is a device which is operated from a distance.
# code:
int pin1=2;
int pin2=3;
void setup() {
Serial.begin(9600);
pinMode(pin1,OUTPUT);
pinMode(pin2,OUTPUT);
}

void loop() {
  if(Serial.available()>0)
   {     
      char data= Serial.read(); // reading the data received from the bluetooth module
      switch(data)
      {
case 'a': { digitalWrite(pin1,HIGH);//FORWARD
            digitalWrite(pin2,LOW);}
            break;
case 'b'  : {digitalWrite(pin1,LOW);//FORWARD
            digitalWrite(pin2,HIGH);} //BACK
              break;
case 'c'  :{digitalWrite(pin1,LOW);//STOP
            digitalWrite(pin2,LOW);}
            break;
default : break;
      }
      Serial.println(data);
   }
   delay(50);
}
# Explanation:
Smartbin is operated by using bluetooth module. We can operate it with any device from anywhere(10 meters range).It opens when 'a' command is given and closes when 'b' command is given.
It has a motor.This motor acts like open and close gate.
This motor is operated by a LN_28 motor driver.
# Other Applications
>Smart Garage.

>Smart Gate.

>Smart Door.
![smartbin](https://user-images.githubusercontent.com/91971716/136941421-85bf7530-4d60-4025-bb17-30d1ae923410.jpg)
![smartbin](https://user-images.githubusercontent.com/91971716/136941561-0364afd1-5dce-4b09-a0ff-6b4170107efb.gif)
