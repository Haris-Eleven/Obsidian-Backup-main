# MicroC + Proteus
## Info 
> PIC16F84A
  Animated LED Red model
  1/8 watt resistor 220 ohm
  In Proteus set f = 8MHz
1. Code for Led Blink
![[Pasted image 20251111224451.png]]
![[Pasted image 20251111224455.png]]
2. 7 segment display common cathode
![[Pasted image 20251111230203.png]]
![[Pasted image 20251111230813.png]]
3. Stepper Motor
> ULN2003a
```C
void main() {
	TRISB = 0x00; // Set PORTB as output
	PORTB = 0x00; // Initialize PORTB
	
	while(1) {
	
	PORTB = 0b0001; // For sequence 0001
	Delay_ms(200); // Delay of 200 ms
	
	PORTB = 0b0010; // For sequence 0010
	Delay_ms(200); // Delay of 200 ms
	
	PORTB = 0b0100; // For sequence 0100
	Delay_ms(200); // Delay of 200 ms
	
	PORTB = 0b1000; // For sequence 1000
	Delay_ms(200); // Delay of 200 ms

	}
}
```
![[Pasted image 20251111233544.png]]
4. Keypad 
```C
unsigned short KP = 0;
char keypadPort at PORTB ;
 void main () {
 TRISA = 0 x00 ;
 PORTA = 0 x00 ;
 Keypad_Init () ;

 while (1) {
	 do {
	 KP = Keypad_Key_Press () ;
	 } while (! KP ) ;
	
	 if (( KP <= 3) ) {
	 PORTA = KP ;
	 }
	 else if (( KP > 3) && ( KP <= 7) ) {
	 PORTA = KP - 1;
	 }
	 else if (( KP > 7) && ( KP <= 11) ) {
	PORTA = KP - 2;
	}
 }
}
```
![[Pasted image 20251112005956.png]]
# Arduino 
## UART
> Tx -> Rx 
> Gnd -> Gnd

Transmitter 
```c
void setup() {
  Serial.begin(9600);
}
void loop() {
  Serial.println("Hello from A");
  delay(1000);
}

```
Reciever
```C
void setup() {
  Serial.begin(9600);
}
void loop() {
  if (Serial.available()) {
    Serial.println(Serial.readString());
  }
}
```
## SPI
|SPI Signal|Master (Board A)|Slave (Board B)|
|---|---|---|
|MOSI|11|11|
|MISO|12|12|
|SCK|13|13|
|SS|10|10|
|GND|GND|GND|
Master
```C
#include <SPI.h>
void setup() {
  SPI.begin();
  pinMode(10, OUTPUT);
}
void loop() {
  digitalWrite(10, LOW);
  SPI.transfer('A');
  digitalWrite(10, HIGH);
  delay(1000);
}

```
Slave
```C
#include <SPI.h>
volatile byte data;
void setup() {
  SPI.begin();
  SPCR |= _BV(SPE);
  pinMode(MISO, OUTPUT);
  SPI.attachInterrupt();
  Serial.begin(9600);
}
ISR(SPI_STC_vect) {
  data = SPDR;
}
void loop() {
  if (data) {
    Serial.println((char)data);
    data = 0;
  }
}

```
## I2C
|Signal|Master (Board A)|Slave (Board B)|
|---|---|---|
|SDA|A4|A4|
|SCL|A5|A5|
|GND|GND|GND|

Master
```C
#include <Wire.h>

void setup() {
  Wire.begin(); 
  Serial.begin(9600);
  Serial.println("I2C Master Ready");
}

void loop() {
  Wire.beginTransmission(0x08);
  Wire.write("Hello");         
  Wire.endTransmission();      
  Serial.println("Data sent to slave");
  delay(1000);
}
```

Slave
```C
#include <Wire.h>
#include <Wire.h>

void setup() {
  Wire.begin(0x08);
  Wire.onReceive(receiveEvent); 
  Serial.begin(9600);
  Serial.println("I2C Slave Ready");
}

void loop() {
  delay(100);
}

void receiveEvent(int howMany) {
  while (Wire.available()) {
    char c = Wire.read(); 
    Serial.print(c);
  }
  Serial.println();
}

```

## USB
only on 1 arduino
```C
void setup() {
  Serial.begin(9600);         // start USB serial at 9600 baud
  Serial.println("Hello PC via USB!");
}

void loop() {
  Serial.println(millis());   // print uptime every second
  delay(1000);
}
```

## FIR
**FIR (Finite Impulse Response)**
- Output depends _only_ on current and past input samples.
- Always stable.
- Uses **no feedback**
- Easy to design, predictable, but can need more coefficients.
**IIR (Infinite Impulse Response)**
- Output depends on both input and _previous outputs_.
- Uses **feedback**, so it’s more efficient (fewer coefficients) but can go unstable if you mess up.

FIR
```C
#define N 3
float x[N];
float coeffs[N] = {1.0/N, 1.0/N, 1.0/N};

float fir(float newSample) {
  for (int i = N - 1; i > 0; i--) x[i] = x[i - 1];
  x[0] = newSample;
  float y = 0;
  for (int i = 0; i < N; i++) y += coeffs[i] * x[i];
  return y;
}

void setup() {
  Serial.begin(9600);
}

void loop() {
  static int n = 0;
  float t = n * 0.1;                        // fake time
  float input = sin(t) * 100 + random(-10, 10);  // noisy sine wave
  float output = fir(input);

  Serial.print(input); Serial.print(","); Serial.println(output); // for plotting
  n++;
  delay(50);
}


```

IIR
```C
float alpha = 0.1; // 0 < alpha < 1  (smaller = smoother)
float y = 0;

void setup() {
  Serial.begin(9600);
}

void loop() {
  static int n = 0;
  float t = n * 0.1;
  float input = sin(t) * 100 + random(-10, 10);  // noisy sine
  y = y + alpha * (input - y);                   // IIR filter
  Serial.print(input); Serial.print(","); Serial.println(y);
  n++;
  delay(50);
}

```

# STM32 Nucleo
Board: NUCLEO-f446RE 

# Arm cortex
IAR Workbench + Flash loader
![[Pasted image 20251112020312.png]]
Copy Both INC and stm_lib.a and paste in ur project folder
https://drive.google.com/file/d/1meNjgHkUCpVf_o0gCG1ZfmHYnv3voODB/view?usp=sharing

# PIC Kit
Mplab + PIC bootloader 
https://drive.google.com/file/d/11sJsyGyD8lMKK-p0VVcJSPTj9sWYV263/view?usp=sharing
