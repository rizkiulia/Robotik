#include <Servo.h>
#include <SoftwareSerial.h>

int trigPin = 9;
int echoPin = 10;
int led = 7;
SoftwareSerial mySerial(4, 5); 
Servo servo;
int sound = 250;

void setup() {
  // put your setup code here, to run once:

  Serial.begin (9600);
  pinMode(led, OUTPUT);
  pinMode(trigPin, OUTPUT);
  pinMode(echoPin, INPUT);

  servo.attach(8);
}

void loop() {
  // put your main code here, to run repeatedly:

  long duration, distance;
  digitalWrite(trigPin, HIGH);
  delayMicroseconds(1000);
  digitalWrite(trigPin, LOW);
  duration=pulseIn(echoPin, HIGH);
  distance=(duration/2)/29.1;
  Serial.print(distance);
  Serial.println("CM");
  delay(10);

  if((distance<=10))
  {
    digitalWrite(led, HIGH);
    }
    else if(distance>10)
    {
      digitalWrite(led, LOW);
      }

   if(distance<5){
    servo.write(90);
    }
    else{
      servo.write(0);
      }

   if (distance>60||distance<=0){
    Serial.println("The distance is more than 60");
    }
    else{
      Serial.print(distance);
      Serial.println("cm");
      }
      delay(500);
}
