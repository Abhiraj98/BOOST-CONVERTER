# BOOST-CONVERTER
void setup() {
  // put your setup code here, to run once:
Serial.begin(9600);
pinMode(9,OUTPUT);
TCCR1B=TCCR1B & 0b11111000 | 0x02; //changing frequnecy to 3.902 KHZ
}

void loop() {
  // put your main code here, to run repeatedly:
analogWrite(9,100);
delay(10);
}
