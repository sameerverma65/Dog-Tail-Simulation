#include <ESP32Servo.h>

const int servoPin = 16;
const int led = 23;
const int echo = 32;
const int trigger = 33;
const int button = 35;
bool isPressed = false;
Servo servo;

void wag_tail(int speed){
  for(int i=90; i>=35; i--){
    if(button_press()) return;
    servo.write(i);
    delay(speed);
  }
  for(int i=45; i<=145; i++){
    if(button_press()) return;
    servo.write(i);
    delay(speed);
  }
  for(int i=145; i>=90; i--){
    if(button_press()) return;
    servo.write(i);
    delay(speed);
  }
}

bool button_press(){
  if(digitalRead(button) == HIGH){
    isPressed = true;
    return true;
  }
  return false;
}

void setup(){
  Serial.begin(115200);
  pinMode(trigger, OUTPUT);
  pinMode(echo, INPUT);
  pinMode(led, OUTPUT);
  pinMode(button, INPUT);
  servo.attach(servoPin);
  servo.write(90);
}

void loop(){
  if (digitalRead(button) == HIGH || isPressed) {
    servo.write(90);
    delay(3000);
    isPressed = false;
    return;
  }
  digitalWrite(trigger, LOW);
  delayMicroseconds(2);
  digitalWrite(trigger, HIGH);
  delayMicroseconds(10);
  digitalWrite(trigger, LOW);

  long duration = pulseIn(echo, HIGH);
  double distance = (duration * 0.0343) / 2;
  Serial.print("Cm: ");
  Serial.print(distance);
  Serial.println();
  if(distance > 50.0){
    digitalWrite(led, LOW);
    wag_tail(6);
  }else if(distance >= 10 && distance <= 50){
    digitalWrite(led, LOW);
    wag_tail(2);
  }else{
    digitalWrite(led, HIGH);
  }
  delay(5);
}
