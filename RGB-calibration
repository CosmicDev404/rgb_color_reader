const int r = 3;  //red LED 
const int g = 5;  //green LED 
const int b = 6;  //blue LED
const int gb_i= 50;  //intensity of green & blue LEDs
const int r_i = 255;  //intensity of red LED

void setup() {
  pinMode(r, OUTPUT);
  pinMode(g, OUTPUT);
  pinMode(b, OUTPUT);
}

void loop() {
  emit(r, r_i);
  emit(g, gb_i);
  emit(b, gb_i);
  delay(500);
}

void emit(int color, int intensity){  //usig function to avoid conflicts in delays and keeping the code DRY
  analogWrite(color, intensity);
  delay(50);
  analogWrite(color, 0);
  delay(50);
}
