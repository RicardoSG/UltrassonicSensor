//ultrassonico1

#define trig1 23
#define echo1 2 //interrupcao1

//ultrassonico2

#define trig2 27
#define echo2 3 //interrupcao2

//ultrassonico3

#define trig3 31
#define echo3 18 //interrupcao3

//ultrassonico4

#define trig4 35
#define echo4 19 //interrupcao4

volatile unsigned long LastPulseTime1;
volatile unsigned long LastPulseTime2;
volatile unsigned long LastPulseTime3;
volatile unsigned long LastPulseTime4;

void setup() {
  Serial.begin(9600);
  pinMode(trig1,OUTPUT);
  pinMode(echo1,INPUT);
  pinMode(trig2, OUTPUT);
  pinMode(echo2, INPUT);
  pinMode(trig3, OUTPUT);
  pinMode(echo3, INPUT);
  pinMode(trig4, OUTPUT);
  pinMode(echo4, INPUT);

  attachInterrupt(0, Echo1_ISR, RISING); //pino 2
  attachInterrupt(1, Echo2_ISR, RISING); //pino 3
  attachInterrupt(2, Echo3_ISR, RISING); //pino 18
  attachInterrupt(3, Echo4_ISR, RISING); //pino 19
}
void loop() {

    digitalWrite(trig1,HIGH);
    digitalWrite(trig2, HIGH);
    digitalWrite(trig3, HIGH);
    digitalWrite(trig4, HIGH);
    delayMicroseconds(10);
    digitalWrite(trig1,LOW);
    digitalWrite(trig2,LOW);
    digitalWrite(trig3,LOW);
    digitalWrite(trig4,LOW);

  Serial.print("Ultrassonico 1  ");
  Serial.print(LastPulseTime1);
  Serial.print('\t');
  Serial.print((LastPulseTime1/2) / 29.1,1);
  Serial.println("cm");

  Serial.print("Ultrassonico 2 ");
  Serial.print(LastPulseTime2);
  Serial.print('\t');
  Serial.print((LastPulseTime2/2) / 29.1,1);
  Serial.println("cm");

  Serial.print("Ultrassonico 3  ");
  Serial.print(LastPulseTime3);
  Serial.print('\t');
  Serial.print((LastPulseTime3/2) / 29.1,1);
  Serial.println("cm");

  Serial.print("Ultrassonico 4  ");
  Serial.print(LastPulseTime4);
  Serial.print('\t');
  Serial.print((LastPulseTime4/2) / 29.1,1);
  Serial.println("cm");
}


void Echo1_ISR()
{
  static unsigned long startTime1;

  if (digitalRead(echo1))
    startTime1 = micros();
    else
      LastPulseTime1 = micros() - startTime1;
}

void Echo2_ISR()
{
  static unsigned long startTime2;

  if (digitalRead(echo2))
    startTime2 = micros();
    else
      LastPulseTime2 = micros() - startTime2;
}

void Echo3_ISR()
{
  static unsigned long startTime3;

  if (digitalRead(echo3))
    startTime3 = micros();
    else
      LastPulseTime3 = micros() - startTime3;
}

void Echo4_ISR()
{
  static unsigned long startTime4;

  if (digitalRead(echo4))
    startTime4 = micros();
    else
      LastPulseTime4 = micros() - startTime4;
}
