int touchPin = 2;

void setup() {
  pinMode(touchPin, INPUT_PULLUP);  // IMPORTANT CHANGE
  Serial.begin(9600);
}

void loop() {
  if (digitalRead(touchPin) == LOW) {  // note LOW instead of HIGH
    Serial.println("TOUCH");
    delay(300);
  }
}
