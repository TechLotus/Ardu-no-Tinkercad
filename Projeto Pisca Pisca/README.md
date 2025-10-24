 **Código**

int leds[] = {2, 3, 4, 5, 6}; // reconhece os pinos dos LEDS
int tempo = 3000;             // determina o tempo em segundos

void setup() {
  for (int i = 0; i < 5; i++) {  // estabelece uma ordem a seguir
    pinMode(leds[i], OUTPUT);
  }
}

void loop() {
  for (int i = 0; i < 5; i++) {  // estabelece qual LED vai ligar ou desligar e parte pro próximo
    digitalWrite(leds[i], HIGH); 
    delay(tempo);                
    digitalWrite(leds[i], LOW);  
  }
}
