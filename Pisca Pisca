*Descrição*

O primeiro projeto é o pisca pisca, onde foi feito um sistema que liga o primeiro LED por 3 segubdos e após apagar, liga o próximo e assim sucessivamente até voltar novamente ao início.

*Materiais*

- 1 Arduíno Uno
- 1 Placa de Ensaio
- 5 LEDS
- 5 Resistores 220 Ohns

*Código*

int leds[] = {2, 3, 4, 5, 6}; 
int tempo = 3000;              

void setup() {
  for (int i = 0; i < 5; i++) {
    pinMode(leds[i], OUTPUT);
  }
}

void loop() {
  for (int i = 0; i < 5; i++) {
    digitalWrite(leds[i], HIGH); 
    delay(tempo);                
    digitalWrite(leds[i], LOW);  
  }
}

