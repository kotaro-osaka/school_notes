# RGB LED
___
**Legs**
- Red
- Anode/Cathode
- Green
- Blue

**Anode/Cathode**
- Longest leg
- Anode: `5v`
- Cathode: `GND`

**Setup**
```cpp
int redPin = 11;
int greenPin = 9;
int bluePin = 10;

void setup() {
	pinMode(redPin, OUTPUT);
	pinMode(greenPin, OUTPUT);
	pinMode(bluePin, OUTPUT);
}
```

**On/Off**
```cpp
digitalWrite(redPin, HIGH);
digitalWrite(redPin, LOW);
```

**Pulse Width Modulation (PWM)**
- Supported by Pins with `~`
- Sends frequent pulses
	- More pulses = Brighter

**Color blending**
```cpp
// min 0
// max 255
void setColor(int red, int green, int blue) {
	analogWrite(redPin, red);
	analogWrite(greenPin, green);
	analogWrite(bluePin, blue);
}
```

**Widerstand**
$R= \frac{U}{I}$
- $I=35mA$
- $rot: U=2,5V$ $R≈71,43Ω$
- $grün:U=4V$ $R≈114,29Ω$
- $blau:U=4V$ $R≈114,29Ω$

___
[YouTube](https://youtu.be/5Qi93MjlqzE)