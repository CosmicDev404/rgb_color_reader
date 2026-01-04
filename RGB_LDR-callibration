const int r = 3;
const int g = 5;
const int b = 6;
const int g_i = 200;
const int b_i = 255;
const int r_i = 179;
const int ldr = A0;
int val_R = 0;
int val_G = 0;
int val_B = 0;
int avg[3] = {0,0,0};
int noise = 60;

void setup() {
  pinMode(r, OUTPUT);
  pinMode(g, OUTPUT);
  pinMode(b, OUTPUT);
  pinMode(ldr, INPUT);
  Serial.begin(9600);
}

void loop() {
  processRGB();
  Serial.println(avg[0]);
  Serial.println(avg[1]);
  Serial.println(avg[2]);
  for(int j = 0; j<2; j++){
    color_mapper(avg[0], avg[1], avg[2]);
  }
  Serial.println(color_mapper(avg[0], avg[1], avg[2]));
}

void emit(int color, int intensity, int &val){
  analogWrite(color, intensity);
  delay(50);
  val = analogRead(ldr);
  analogWrite(color, 0);
  delay(50);
}

void sample(){
  emit(r, r_i, val_R);
  emit(g, g_i, val_G);
  emit(b, b_i, val_B);
}

void processRGB(){
  int RED = 0;
  int GREEN = 0;
  int BLUE = 0;
  for(int i = 0; i<5; i++){
    sample();
    RED = val_R + RED;
    GREEN = val_G + GREEN;
    BLUE = val_B + BLUE;
  }
  RED = RED / 5;
  GREEN = GREEN / 5;
  BLUE = BLUE/ 5;
  int RED_norm = map(RED, 0, 574, 0, 255);
  int GREEN_norm = map(GREEN, 0, 376, 0, 255);
  int BLUE_norm = map(BLUE, 0, 303, 0, 255);
  avg[0] = RED_norm;
  avg[1] = GREEN_norm;
  avg[2] = BLUE_norm;
}
char* color_mapper(int R, int G, int B) {
  static char color[10];
  int clr = R+G+B;
  if (clr < 40) {
  strcpy(color, "Black");
  return color;
  }
  if(R>2*G && R>2*B && (G-B<=noise || B-G<=noise)){
    strcpy(color, "Red");
  }else if(G>2*B && G>2*R && (R-B<=noise || B-R<=noise)){
    strcpy(color, "Green");
  }else if(B>2*G && B>2*R && (G-R<=noise || R-G<=noise)){
    strcpy(color, "Blue");
  }else if (R-B>=noise && G<=2*noise && R>2*G){
    strcpy(color, "Pink");
  }else if (R-G<=noise && R>=2*B){
    strcpy(color, "Yellow");
  }else if (R-B<=noise && G<=noise && R>G){
    strcpy(color, "Purple");
  }else if (R>2*G && G>2*B && B<=noise){
    strcpy(color, "Orange");
  }else if (R>2*G && R-B>=2*noise && B<=noise){
    strcpy(color, "Brown");
  }else if (B-G<=noise && B>2*R && R<=noise){
    strcpy(color, "Cyan");
  }else if(B>R && B>G && R-G>=2*noise && B-R>=2*noise && B-G>=noise){
    strcpy(color, "Sky Blue");
  }else if(R-G<=noise && G-B<=noise && B-G<=noise){
    if(R>41 && R<=205){
      strcpy(color, "Gray");
    }else{
      strcpy(color, "White");
    }
  }else{
    strcpy(color, "unknown");
  }
  return color;
}
