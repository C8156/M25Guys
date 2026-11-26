# M25Guys

const int trigPin = 7;
const int echoPin = 8;


void setup() {
  Serial.begin(115200);d:\Page_Code_Final\Page_Code_Final.ino

  pinMode(trigPin, OUTPUT);
  pinMode(echoPin, INPUT);
}

void loop() {
  long duration;
  delayMicroseconds(2);

  digitalWrite(trigPin, HIGH);
  delayMicroseconds(10);
  digitalWrite(trigPin, LOW);

  long duration = pulseIn(echoPin, HIGH, 30000);

  float distance = duration * 0.034 / 2;

  Serial.print("Distance: ");
  Serial.print(distance);
  Serial.println(" cm");

  if (duration > 0 && distance <= 20.32) {
    digitalWrite(ledPin, HIGH);
    delay(250);
    digitalWrite(ledPin, LOW);
    delay(250);
  } else {
    digitalWrite(ledPin, LOW);
    delay(100);
  }
}
