# BT-car-code-for-Arduno.
This is my first Git Repositry,
//Made by Balwant Khati //
#define spree 9
#define dreel 8
#define horn 7
#define cutter 6
char t;
 void setup() 
{
pinMode(13,OUTPUT); //left motors forward
pinMode(12,OUTPUT); //left motors reverse
pinMode(11,OUTPUT); //right motors forward
pinMode(10,OUTPUT); //right motors reverse
pinMode(spree,OUTPUT); //spree/W
pinMode(dreel,OUTPUT); //drell/U
pinMode(horn,OUTPUT); //horn /V
pinMode(cutter,OUTPUT); //cuttr/x
pinMode(4,OUTPUT); //horn 
pinMode(5,OUTPUT); //wait led
pinMode(3,OUTPUT); //red
pinMode(2,INPUT); //ir
Serial.begin(9600);
 }
 void loop() 
{
if(Serial.available()>0)
{
 t = Serial.read();
 Serial.println(t);
}
 
int Speed = t; // 0 - 255
 if(t== '0');
{
 digitalWrite(5,HIGH);
 Speed = 100;
}
if(t=='1')
{
 digitalWrite(5,HIGH);
 Speed = 140;}
else if(t=='2')
{
 digitalWrite(5,HIGH);
 Speed = 153;
} 
 else if(t=='3')
{
 digitalWrite(5,HIGH);
 Speed = 165;
}
 else if(t=='4')
{
 Speed = 178;
}
 else if(t== '5')
{
 Speed = 191;
 }
 else if(t=='6')
{
 Speed = 204;
 }
 else if(t=='7')
{
 Speed = 216;
} 
 else if(t=='8')
{
 Speed = 229;
}
 
 else if(t=='9')
{
 digitalWrite(5,LOW);
 Speed = 242;
}
 else if(t=='q')
{
 digitalWrite(5,LOW);
 Speed=255;
} 
 if(t == 'F')
{ 
 //move forward(all motors rotate in forward direction)
 analogWrite(13,Speed);
 analogWrite(12,Speed);
 analogWrite(11,Speed);
 analogWrite(10,Speed);
}
 else if(t == 'B')
{ //move reverse (all motors rotate in reverse direction)
 analogWrite(13,Speed);
 analogWrite(12,Speed);
 analogWrite(11,Speed);
 analogWrite(10,Speed);
 analogWrite(3,Speed);
}
 
else if(t == 'L')
{ //turn right (left side motors rotate in forward direction, right side motors doesn't rotate
 analogWrite(13,Speed);
 analogWrite(12,Speed);
 analogWrite(11,Speed);
 analogWrite(10,Speed);
}
else if(t=='I')
{
 analogWrite(13,Speed);
 analogWrite(12,Speed);
 analogWrite(11,Speed);
 analogWrite(10,Speed);
 }
else if(t=='J')
{
 analogWrite(13,Speed);
 analogWrite(12,Speed);
 analogWrite(11,Speed);
 analogWrite(10,Speed);
 }
else if(t=='G')
{
 analogWrite(13,Speed);
 analogWrite(12,Speed);
 analogWrite(11,Speed);
 analogWrite(10,Speed);
 }
else if(t=='H')
{
 analogWrite(13,Speed);
 analogWrite(12,Speed);
 analogWrite(11,Speed);
 analogWrite(10,Speed);
 }
 else if(t == 'R')
{ 
 analogWrite(13,Speed);
 analogWrite(12,Speed);
 analogWrite(11,Speed);
 analogWrite(10,Speed);
}
else if(t == 'W')
{ 
 digitalWrite(9,HIGH);
}
else if(t == 'w')
{
 digitalWrite(9,LOW);
}
 else if(t == 'U')
{ 
 digitalWrite(8,HIGH);
}
else if(t == 'u')
{
 digitalWrite(8,LOW);
}
 else if(t == 'X')
{digitalWrite(6,HIGH);
}
else if(t == 'x')
{
 digitalWrite(6,LOW);
}
 else if(t == 'V')
{ 
 digitalWrite(7,HIGH);
}
else if(t == 'v'){
 digitalWrite(7,LOW);
}
 else if(t == 'S')
{ 
 analogWrite(13,Speed);
 analogWrite(12,Speed);
 analogWrite(11,Speed);
 analogWrite(10,Speed);
 digitalWrite(3,HIGH);
}
delay(10);
 int irValue = digitalRead (2);
if (irValue == 1)
{
 digitalWrite(4, HIGH);
 digitalWrite(13,LOW);
 digitalWrite(12,LOW);
 digitalWrite(11,LOW);
 digitalWrite(10,LOW);
 digitalWrite(3,HIGH);
}
 if (irValue == 0)
{
 digitalWrite(4, LOW);
 digitalWrite(3,LOW);
}
}
