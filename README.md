# Smart-Home-with-Arduino-and-Motion-Sensor
A simple smart home system using Arduino and a motion sensor.
const int motionSensorPin = 2;
const int ledPin = 13;

void setup() {
    pinMode(motionSensorPin, INPUT);
    pinMode(ledPin, OUTPUT);
    Serial.begin(9600);
}

void loop() {
    int motionValue = digitalRead(motionSensorPin);

    if (motionValue == HIGH) {
        Serial.println("Motion detected!");
        digitalWrite(ledPin, HIGH);
        delay(5000);  // Light stays on for 5 seconds
        digitalWrite(ledPin, LOW);
    }

    delay(1000);  // Pause for a second
}
