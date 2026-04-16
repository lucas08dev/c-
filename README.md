// Atribuição de tags símbolos aos pinos
// cons int led_red = 5

#define led_red 5
#define led_yel 7
#define led_gre 11

// Variável global
int valor = 0;

void setup() {
// Configuração dos sentidos dos pinos de input (I/O)
pinMode(led_red, OUTPUT);
pinMode(led_gre, OUTPUT);
pinMode(led_yel, OUTPUT);

// Habilitar comunicação serial do Arduino UNO
// Velocidade (baud rate) 9600 bits/s
Serial.begin(9600);
// Mensagens de inicialização 
Serial.println("#####################");
Serial.println("1CCPG - SERS - 2026");
Serial.println("Inicializacao concluida");
Serial.println("#####################");

delay(4000); // 4 segundos para o início do loop

}

void loop() {
  /*
  1.Ligar os três LED's simultaneamente por 3 segundos
  2.Desligar por 1 segundo
  3.Reiniciar
  */

digitalWrite(led_gre, HIGH);
digitalWrite(led_red, HIGH);
digitalWrite(led_yel, HIGH);
delay(3000);
Serial.println("Fase 1 concluida");
digitalWrite(led_gre, LOW);
digitalWrite(led_red, LOW);
digitalWrite(led_yel, LOW);
delay(1000);
Serial.println("Fase 2 concluida");
}
