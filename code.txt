#include <Servo.h>

Servo myservo;

const int servoPin = 9;
const int buttonPin = 12;
const int ledPin = 13;

void setup() {
  myservo.attach(servoPin);
  pinMode(buttonPin, INPUT);
  digitalWrite(buttonPin, HIGH);
  pinMode(ledPin, OUTPUT);
  digitalWrite(ledPin, LOW);
  myservo.write(180);
  delay(1000);
  myservo.detach();
}

void loop() {
  int buttonVal = digitalRead(buttonPin);
  if(buttonVal == LOW) {
    myservo.attach(servoPin);
    myservo.write(30);
    delay(575);
    myservo.write(180);
    delay(1500);
    myservo.detach();
    delay(5000);
  }
  delay(13);
}
