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

float minimum;

void setup() {
  pinMode(r, OUTPUT);
  pinMode(g, OUTPUT);
  pinMode(b, OUTPUT);
  pinMode(ldr, INPUT);
  Serial.begin(9600);
}

void loop() {
  processRGB();
  Serial.println(avg[0]); //RED
  Serial.println(avg[1]); //GREEN
  Serial.println(avg[2]); //BLUE
  Serial.println(color_mapper(0, int(avg[0]), int(avg[1]), int(avg[2])));  //color name
  Serial.println(minimum); 
  Serial.println(color_mapper(1, int(avg[0]), int(avg[1]), int(avg[2])));  //color name
  Serial.println(minimum); 
  Serial.println(color_mapper(2, int(avg[0]), int(avg[1]), int(avg[2])));  //color name
  Serial.println(minimum); 
}

void emit(int color, int intensity, int &val){  //just emits each color and read the LDR values
  analogWrite(color, intensity);
  delay(50);
  val = analogRead(ldr);
  analogWrite(color, 0);
  delay(50);
}

void sample(){  //emits and store the readings for RGB
  emit(r, r_i, val_R);
  emit(g, g_i, val_G);
  emit(b, b_i, val_B);
}

void processRGB(){  //normalizes RGB readings and maps them to same intensity for further processing
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
  int RED_norm = map(RED, 0, 467, 0, 255);  //fine tuned by from the reflection of a white surface
  int GREEN_norm = map(GREEN, 0, 229, 0, 255);  //fine tuned by from the reflection of a white surface
  int BLUE_norm = map(BLUE, 0, 195, 0, 255);  //fine tuned by from the reflection of a white surface
  avg[0] = RED_norm;
  avg[1] = GREEN_norm;
  avg[2] = BLUE_norm;
}

char* color_mapper(int mode, int R, int G, int B) { //passes color names for inputted RGB codes
  static char color[50];
  //float minimum;
  float red;
  float green;
  float blue;
  float cyan;
  float magenta;
  float yellow;
  float orange;
  float kesari; //the Indian Saffron
  float CBrown;
  float Lgreen;
  float indigo;
  float saffron;
  float pink;
  float wheat;
  float gold;
  float turquoise;
  float white;
  float gray;
  float teal;
  float plotR[3] = {255-R, G, B};
  avg_arr(plotR, red);
  float plotG[3] = {R, 255-G, B};
  avg_arr(plotG, green);
  float plotB[3] = {R, G, 255-B};
  avg_arr(plotB, blue);
  float plotC[3] = {R, 255-G, 255-B};
  avg_arr(plotC, cyan);
  float plotM[3] = {255-R, G, 255-B};
  avg_arr(plotM, magenta);
  float plotY[3] = {255-R, 255-G, B};
  avg_arr(plotY, yellow);
  float plotO[3] = {255-R, abs(165-G), B};
  avg_arr(plotO, orange);
  float plotK[3] = {255-R, abs(119-G), abs(34-B)};
  avg_arr(plotK, kesari);
  float plotCB[3] = {abs(187-R), abs(142-G), abs(81-B)};
  avg_arr(plotCB, CBrown);
  float plotLG[3] = {abs(50-R), abs(205-G), abs(50-B)};
  avg_arr(plotLG, Lgreen);
  float plotI[3] = {abs(75-R), G, abs(130-B)};
  avg_arr(plotI, indigo);
  float plotSaffron[3] = {abs(255-R), abs(183-G), abs(206-B)};
  avg_arr(plotSaffron, saffron);
  float plotpink[3] = {abs(251-R), abs(116-G), abs(168-B)};
  avg_arr(plotpink, pink);
  float plotwheat[3] = {abs(245-R), abs(222-G), abs(179-B)};
  avg_arr(plotwheat, wheat);
  float plotgold[3] = {abs(229-R), abs(184-G), abs(11-B)};
  avg_arr(plotgold, gold);
  float plottur[3] = {abs(4-R), abs(255-G), abs(247-B)};
  avg_arr(plottur, turquoise);
  float plotwhite[3] = {abs(255-R), abs(255-G), abs(255-B)};
  avg_arr(plotwhite, white);
  float plotgray[3] = {abs(128-R), abs(128-G), abs(128-B)};
  avg_arr(plotgray, gray);
  float plotteal[3] = {R, abs(128-G), abs(128-B)};
  avg_arr(plotteal, teal);

  if (mode==0){
    float val_array[3]= {red, blue, green};
    min_finder(val_array, 3, minimum);
  }
  if (mode==1){
    float val_array[3]= {cyan, magenta, yellow};
    min_finder(val_array, 3, minimum);
  }
  if (mode==2){
    float val_array[19]= {red, blue, green, cyan, magenta, yellow, orange, kesari, CBrown, Lgreen, indigo, saffron, pink, wheat, gold, turquoise, white, gray, teal};
    min_finder(val_array, 19, minimum);
  }


  if(minimum==cyan){  // CMY
    strcpy(color, "Cyan");
  }else if(minimum==magenta){
    strcpy(color, "Magenta");
  }else if(minimum==yellow){
    strcpy(color, "Yellow");
  }else if(minimum==red){ //RGB
    strcpy(color, "Red");
  }else if(minimum==green){
    strcpy(color, "Green");
  }else if(minimum==blue){
    strcpy(color, "Blue");
  }else if(minimum==orange){  //tirtiary colors and others
    strcpy(color, "Orange");
  }else if(minimum==kesari){
    strcpy(color, "Kesari");
  }else if(minimum==CBrown){
    strcpy(color, "Cardboard Brown");
  }else if(minimum==Lgreen){
    strcpy(color, "Lime Green");
  }else if(minimum==indigo){
    strcpy(color, "Indigo");
  }else if(minimum==saffron){
    strcpy(color, "Saffron");
  }else if(minimum==pink){
    strcpy(color, "Pink");
  }else if(minimum==wheat){
    strcpy(color, "Wheat");
  }else if(minimum==gold){
    strcpy(color, "Gold");
  }else if(minimum==turquoise){
    strcpy(color, "Turquoise");
  }else if(minimum==white){ //neutrals
    strcpy(color, "White");
  }else if(minimum==gray){
    strcpy(color, "Gray");
  }else if(minimum==teal){
    strcpy(color, "Teal");
  }else{strcpy(color, "!error!");}  //can only occur when logic fails silently
  return color;
}

int avg_arr(float array_to_be_averaged[], float &avg_found){  //makes the average value for the color inputted
  avg_found=0;
  for(int j = 0; j<3; j++){
    avg_found+=array_to_be_averaged[j];
  }
  avg_found=avg_found/3;
  return avg_found;
}
int min_finder(float ARRAY[], int size, float &smallest){ //finds the minimum value stored in input array
  smallest=255;
  for(int k = 0; k<size; k++){
    if(ARRAY[k]<smallest){
      smallest=ARRAY[k];
    }
  }
  return smallest;  
}
