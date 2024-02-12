// Define pins for ultrasonic sensor, buzzer, and vibration motor
const int trigPin = 2;  // Trig pin of ultrasonic sensor
const int echoPin = 3;  // Echo pin of ultrasonic sensor
const int buzzerPin = 8;  // Buzzer pin
const int vibrationPin = 9;  // Vibration motor pin

void setup() {
  Serial.begin(9600);
  pinMode(trigPin, OUTPUT);
  pinMode(echoPin, INPUT);
  pinMode(buzzerPin, OUTPUT);
  pinMode(vibrationPin, OUTPUT);
}

void loop() {
  // Measure distance using ultrasonic sensor
  long duration, distance;
  digitalWrite(trigPin, LOW);
  delayMicroseconds(2);
  digitalWrite(trigPin, HIGH);
  delayMicroseconds(10);
  digitalWrite(trigPin, LOW);
  duration = pulseIn(echoPin, HIGH);
  distance = duration * 0.034 / 2;

  // Print distance to Serial Monitor
  Serial.print("Distance: ");
  Serial.println(distance);

  // Check if an object is within a certain range (adjust as needed)
  if (distance < 20) {
    // Object detected, produce beep sound and vibration
    beep();
    vibrate();
    delay(1000);  // Adjust the delay as needed
  } else {
    // No object detected, turn off beep and vibration
    noBeep();
    noVibration();
  }
}

// Function to produce beep sound
void beep() {
  tone(buzzerPin, 1000);  // Adjust frequency as needed
}

// Function to turn off beep sound
void noBeep() {
  noTone(buzzerPin);
}

// Function to activate vibration motor
void vibrate() {
  digitalWrite(vibrationPin, HIGH);
}

// Function to turn off vibration motor
void noVibration() {
  digitalWrite(vibrationPin, LOW);
}
