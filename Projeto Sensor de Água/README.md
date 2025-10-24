**Código**

// define nomes de variantes

#define TRIG 9            
#define ECHO 10
#define LED_VERDE 2
#define LED_AMARELO 3
#define LED_VERMELHO 4
#define BOMBA 5

// define as variáveis

long duracao;   
int distancia;

// define a relação do sensor com os LEDS

void setup() {
  pinMode(TRIG, OUTPUT);
  pinMode(ECHO, INPUT);
  pinMode(LED_VERDE, OUTPUT);
  pinMode(LED_AMARELO, OUTPUT);
  pinMode(LED_VERMELHO, OUTPUT);
  pinMode(BOMBA, OUTPUT);
  Serial.begin(9600);
}

// faz uma ação repetitiva

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

// define as distâncias do sensor

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
