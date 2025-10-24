**Descrição**

Este projeto é um sensor que acende um LED branco conforme o nìvel da luz que está no ambiente, onde se estiver escuro ele acende, e caso esteja claro ela apaga.

**Materiais**

- 1 Arduíno Uno
- 1 Placa de Ensaio
- 1 Sensor de Luz Ambiente
- 1 LED
- 1 Resistor de 220 Ohns
- 1 Resistor de 10 Kilo Ohns

**Código**

int sensorLuz = A0;
int led = 9;
int valorLuz;

void setup() {
  pinMode(led, OUTPUT);
  Serial.begin(9600);
}

void loop() {
  valorLuz = analogRead(sensorLuz);
  Serial.print("Luz: ");
  Serial.println(valorLuz);

  if (valorLuz < 500) { 
    digitalWrite(led, HIGH);
  } else { // Claro
    digitalWrite(led, LOW);
  }

  delay(500);
}
