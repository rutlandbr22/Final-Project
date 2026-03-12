# Final-Project
/*
  Pushbutton + Relay Control

  This code reads a pushbutton on pin 2.
  When the button is pressed, the relay connected to pin 4 turns ON.
  When the button is not pressed, the relay turns OFF.

  The relay acts as an electromagnetic switch, allowing a low-power
  Arduino signal to control a higher-power LED circuit.

  Circuit:
  - Pushbutton connected to pin 2
  - 10K resistor from pin 2 to ground
  - Other side of pushbutton to +5V
  - Relay module IN pin connected to pin 4
  - Relay module VCC to 5V
  - Relay module GND to GND

  Note:
  - If your relay is active LOW, reverse the HIGH/LOW values in loop().
*/

// constants won't change
const int buttonPin = 2;   // pushbutton pin
const int relayPin  = 4;   // relay control pin

// variable will change
int buttonState = 0;       // stores pushbutton status

void setup() {
  // set relay pin as output
  pinMode(relayPin, OUTPUT);

  // set button pin as input
  pinMode(buttonPin, INPUT);

  // make sure relay starts off
  digitalWrite(relayPin, LOW);
}

void loop() {
  // read the pushbutton state
  buttonState = digitalRead(buttonPin);

  // if button is pressed, turn relay on
  if (buttonState == HIGH) {
    digitalWrite(relayPin, HIGH);
  } 
  else {
    digitalWrite(relayPin, LOW);
  }
}
