# BOOST-CONVERTER
float value1;
float voltage;
float voltage1;
double current;
float power;
const float vp=0.0048828125;
const float a=2.048;
void setup() 
{
  // put your setup code here, to run once:
Serial.begin(9600);
pinMode(A2,INPUT);

pinMode(9,OUTPUT);
TCCR1B=TCCR1B & 0b11111000 | 0x02; //changing frequnecy to 3.902 KHZ
}

void loop() {
  // put your main code here, to run repeatedly:
value1=analogRead(A3);
voltage1=value1*vp;
voltage=(voltage1*a)+voltage1;
current=voltage1/25;
Serial.println("voltage"+String(voltage));
Serial.println("current"+String(current));
power=voltage*current;
Serial.println("power"+String(power));
analogWrite(9,198);
delay(1);
}
