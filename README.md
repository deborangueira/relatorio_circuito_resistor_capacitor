# relatorio_circuito_resistor_capacitor
Simulação e análise de circuito RC com filtragem, entrada por botão e saída em LEDs.

## Diagrama elétrico e Circuito

<p align="center">
  <figure style="display:inline-block; margin: 10px;">
    <img src="circuito_rc.png" alt="Circuito RC" width="400"/>
    <figcaption><em>Figura 1 - Protótipo do circuito no Tinkercad</em></figcaption>
  </figure>
  <figure style="display:inline-block; margin: 10px;">
    <img src="diagrama_eletrico.png" alt="Diagrama elétrico" width="300"/>
    <figcaption><em>Figura 2 - Diagrama fornecido na atividade</em></figcaption>
  </figure>
</p>


## Análise do circuito com gráficos

Para acessar o notebook [clique aqui](https://github.com/deborangueira/relatorio_circuito_resistor_capacitor/blob/811152a36af3321862d3f7ba4a1e1637a12d664b/src/analise_rc.ipynb).

## Código

```P
int pinoNoRC=0; 
int valorLido = 0;
float tensaoCapacitor = 0, tensaoResistor;
unsigned long time; 

void setup(){ 
Serial.begin(9600); 
} 

void loop() { 
	time=millis(); 
	valorLido=analogRead(pinoNoRC); 
	tensaoCapacitor=(valorLido*5.0/1023); // Lê diretamente a tensão no capacitor
	tensaoResistor = 5.0-tensaoCapacitor; // Calcula a tensão no resistor
 	Serial.print(time); //imprime o conteúdo de time no MONITOR SERIAL
    Serial.print(" "); 
  	Serial.print(tensaoCapacitor);
  	Serial.print(" ");
  	Serial.println(5.0); // Tensão de entrada fixa em 5V
	delay(400); 
}

# Gráficos

### Carga no capacitor
### Carga no resistor
### Comparação carga no capacitor e resistor


```
