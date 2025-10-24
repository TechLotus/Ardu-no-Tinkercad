**Descrição**

Neste daqui, o projeto apresenta um sensor que mede o nível de água de um tanque. Se estiver cheio ele acende um LED vermelho indicando que está cheio adjunto de um LEd azul que representa a bomba d'água. Se estiver médio ele acende um LED amarelo. E caso ele esteja vazio ou quase vazio ele acende um LED verde.

**Materiais**

- 1 Arduíno de UNO
- 1 Placa de Ensaio
- 4 LEDS
- 4 Resistores de 220 Ohns
- 1 Sensor de Distância

**Código**

#define TRIG 9
#define ECHO 10
#define LED_VERDE 2
#define LED_AMARELO 3
#define LED_VERMELHO 4
#define BOMBA 5

long duracao;
int distancia;

void setup() {
  pinMode(TRIG, OUTPUT);
  pinMode(ECHO, INPUT);
  pinMode(LED_VERDE, OUTPUT);
  pinMode(LED_AMARELO, OUTPUT);
  pinMode(LED_VERMELHO, OUTPUT);
  pinMode(BOMBA, OUTPUT);
  Serial.begin(9600);
}

void loop() {
  digitalWrite(TRIG, LOW);
  delayMicroseconds(2);
  digitalWrite(TRIG, HIGH);
  delayMicroseconds(10);
  digitalWrite(TRIG, LOW);

  duracao = pulseIn(ECHO, HIGH);
  distancia = duracao * 0.034 / 2; 

  Serial.print("Distancia: ");
  Serial.print(distancia);
  Serial.println(" cm");

  if (distancia > 20) { 
    digitalWrite(LED_VERDE, HIGH);
    digitalWrite(LED_AMARELO, LOW);
    digitalWrite(LED_VERMELHO, LOW);
    digitalWrite(BOMBA, LOW);
  } 
  else if (distancia <= 20 && distancia > 10) { 
    digitalWrite(LED_VERDE, LOW);
    digitalWrite(LED_AMARELO, HIGH);
    digitalWrite(LED_VERMELHO, LOW);
    digitalWrite(BOMBA, LOW);
  } 
  else if (distancia <= 10) { 
    digitalWrite(LED_VERDE, LOW);
    digitalWrite(LED_AMARELO, LOW);
    digitalWrite(LED_VERMELHO, HIGH);
    digitalWrite(BOMBA, HIGH);
  }

  delay(1000);
}
