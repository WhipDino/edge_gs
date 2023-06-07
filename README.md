Ideia:  

Criarmos um Arduino que, através de um sensor de umidade do solo, calcule a umidade do ambiente para que ajude a diminuir o desperdício de alimento, já que, a umidade não adequada é um dos fatores que contribuem para o desperdício de alimento e ele contribui significamente à fome mundial. Portanto, usaremos o Arduino para duas ocasiões, o primeiro deles é na própria agricultura, onde através do Arduino, ativaria o irrigador agrícola caso a umidade estiver abaixo do recomendado daquele plantio e ativaria os exaustores caso a umidade estiver acima do recomendado. A outra ocasião que seria usado é nos lugares que esses alimentos coletados serão armazenados, uma vez que, a umidade fora do ideal contribui para o desperdício dos alimentos. Neste caso, se o sensor detectar um aumento da umidade acima do limite desejado, ajustaria a ventilação com o uso de desumidificadores. Caso contrário usaria umidificadores. 


Sensor de umidade do solo conectado no pino analógico A0; 

LCD: rs = 12, en = 11, d4 = 5, d5 = 4, d6 = 3, d7 = 2; 

Servo conectado no pino digital 6; 

Led vermelho conectado no pino digital 7; 

Led verde conectado no pino digital 8; 

Led amarelo conectado no pino digital 9; 

Motor CC conectado no pino digital 13 e 10; 



Void setup: 

Serial. begin (9600) configura a comunicação serial para 9600 baud; 

Lcd.begin(16, 2) configura a tela do lcd para 16 colunas e 2 linhas; 

As variáveis ledyellow, ledgreen, ledred, servoPin, motorPin1, motorPin2 foram declaradas como OUTPUT; 

 

Void loop:  

valorUmidade vai ser o valor do sensor de umidade do solo devido a função analogRead que junta os dois através da do pino analógico conectado no sensor de umidade do solo; 

percentage vai mapear através da função map a variável valorUmidade de 0 a 867 (valor máximo do sensor de umidade do solo) de 0 a 100 (transformando esse valor em %); 

Se o valor da percentage for maior que 82 os leds verde e amarelo vão apagar e o led amarelo vai acender. O lcd irá limpar o seu display e mostrar a mensagem "Umidade Alta ". O motor CC vai entrar em um loop de girar para a direita esperar 50 milissegundos e girar para a esquerda; 

Se o valor da percentage estiver entre 15 e 82 os leds amarelo e vermelho vão apagar e o led verde vai acender. O lcd irá limpar o seu display e mostrar a mensagem "Umidade OK "; 

Se o valor da percentage for menor que 15 os leds amarelo e verde vão apagar e o led vermelho vai acender. O lcd irá limpar o seu display e mostrar a mensagem "Umidade Baixa ". o Servo motor vai entrar em um loop de ir para a posição 0 graus e 180 graus; 
