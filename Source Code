#include <SoftwareSerial.h>
int led = 4;
int ldr = A4;
int buzz = 5;
int usstrig1 = 9;
int ussecho1 = 10;
int distance1, walldistance1, duration1;
int usstrig2 = 7;
int ussecho2 = 8;
int distance2, walldistance2, duration2;
SoftwareSerial BTSerial(2, 3); 

bool laserTripped = false;

void setup()
{
  pinMode(led, OUTPUT);
  pinMode(buzz, OUTPUT);
  pinMode(ldr, INPUT);
  pinMode(usstrig1, OUTPUT);
  pinMode(ussecho1, INPUT);
  pinMode(usstrig2, OUTPUT);
  pinMode(ussecho2, INPUT);
  
  Serial.begin(9600);
  BTSerial.begin(9600); 
  
  walldistance1 = measureDistance(usstrig1, ussecho1, duration1);
  walldistance2 = measureDistance(usstrig2, ussecho2, duration2);
  digitalWrite(led, LOW);
  digiralWrite(buzz, LOW);

  BTSerial.println("Room is secured");
  Serial.println("Room is secured");
}

void loop()
{
  int a = analogRead(ldr);
  Serial.println(a);

  if (a < 500)
  {
    if (!laserTripped) {
      laserTripped = true;  
      digitalWrite(led, HIGH);
      digitalWrite(buzz, HIGH);
      BTSerial.println("Laser tripped!");
      Serial.println("Laser tripped!");
    }
  }

  if (laserTripped)
  {
    distance1 = measureDistance(usstrig1, ussecho1, duration1);
    distance2 = measureDistance(usstrig2, ussecho2, duration2);
    
    if (distance1 < walldistance1)
    {
      BTSerial.println("Detected in Room 1");
      Serial.println("Detected in Room 1");
    }
    else
    {
      BTSerial.println("Room 1 is empty");
      Serial.println("Room 1 is empty");
    }

    if (distance2 < walldistance2)
    {
      BTSerial.println("Detected in Room 2");
      Serial.println("Detected in Room 2");
    }
    else
    {
      BTSerial.println("Room 2 is empty");
      Serial.println("Room 2 is empty");
    }
    
    delay(1000); 
  }
}

int measureDistance(int trigPin, int echoPin, int &duration) {
  digitalWrite(trigPin, LOW);
  delayMicroseconds(2);
  digitalWrite(trigPin, HIGH);
  delayMicroseconds(10);
  digitalWrite(trigPin, LOW);
  duration = pulseIn(echoPin, HIGH);
  int measuredDistance = duration * 0.034 / 2;
  
  return measuredDistance;
}
