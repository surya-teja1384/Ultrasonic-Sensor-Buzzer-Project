# Ultrasonic-Sensor-Buzzer-Project.
// defines pins numbers ultrasonic sensor.

const int trigPin = 9;

const int echoPin = 10;



// defines pins numbers buzzer.

const int buzzer = 8;



// defines variables

long duration;

int distance;

void setup() {

pinMode(trigPin, OUTPUT); // Sets the trigPin as an Output

pinMode(echoPin, INPUT); // Sets the echoPin as an Input



pinMode(buzzer, OUTPUT); // Sets the Buzzer as an Output



Serial.begin(9600); // Starts the serial communication

}

void loop() {

// Clears the trigPin

digitalWrite(trigPin, LOW);

delayMicroseconds(2);

// Sets the trigPin on HIGH state for 10 micro seconds

digitalWrite(trigPin, HIGH);

delayMicroseconds(10);

digitalWrite(trigPin, LOW);

// Reads the echoPin, returns the sound wave travel time in microseconds

duration = pulseIn(echoPin, HIGH);

// Calculating the distance

distance= duration*0.034/2;

// Prints the distance on the Serial Monitor

Serial.print("Distance: ");

Serial.println(distance);



if(distance < 50){

   digitalWrite(buzzer, HIGH);

  }else{

     digitalWrite(buzzer, LOW);

    }

}
