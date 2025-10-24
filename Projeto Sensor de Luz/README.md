**Código**

// determina o que está em cada pino

int sensorLuz = A0;
int led = 9;
int valorLuz;

// decide a saída do LED

void setup() {
  pinMode(led, OUTPUT);
  Serial.begin(9600);
}

// define como a luz vai agir no senor, quantidade de luz que está saindo

void loop() {
  valorLuz = analogRead(sensorLuz);
  Serial.print("Luz: ");
  Serial.println(valorLuz);

// ensina como agir conforme a quantidade de luz, se ele acende ou se ele apaga

  if (valorLuz < 500) { 
    digitalWrite(led, HIGH);
  } else { // Claro
    digitalWrite(led, LOW);
  }

// espaço de tempo entre ligar e desligar

  delay(500);
}
