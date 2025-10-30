# Semáforo com Arduino

## 📋 Descrição do Projeto
  Neste projeto busquei desenvolver minhas hab ilidades com arduino e para isso contei de fazer um pequeno projeto. Nele utilizei da função "milis()" para atualizar o tempo em que os led acendiam e mantive um padrão de semáforo.

---

## 🔧 Materiais Necessários

### Hardware
<!-- Liste todos os componentes físicos necessários -->

| Quantidade | Componente | Especificação |
|------------|------------|---------------|
| 1 | Arduino | Modelo (ex: Arduino Uno) |
| 3 | LEDs | Vermelho, Amarelo, Verde |
| 3 | Resistores | 330Ω |
| 1 | Protoboard | - |
| 15 | Jumpers | Macho-Macho / Macho-Fêmea |

### Software
<!-- Liste os softwares necessários -->

- Arduino IDE (versão 1.8.0 ou superior)
- Tinkercad para Prototipação

---

## 📐 Esquema do Circuito

<p align="center">
  <img src="\Images\circuito.png" alt="Circuito TinkerCad" width="400">
  <br>
  <em>Figura 1 – Circuito no TinkerCad</em>
</p>

### Imagem do Circuito
<p align="center">
  <img src="\Images\circuitoReal.jpg" alt="Circuito Real" width="400">
  <br>
  <em>Figura 1 – Circuito Real</em>
</p>

### Vídeo do Circuito Funcionando

Veja o projeto funcionando [aqui](https://drive.google.com/file/d/1chYIdNVb9vkkw7w7YIHkAWr1ue-k4_dK/view?usp=sharing)
---

## 💻 Código

### Estrutura do Código

```cpp
unsigned long TempoAnterior = 0;

void setup(){
  pinMode(8, OUTPUT);
  pinMode(7, OUTPUT);
  pinMode(13, OUTPUT);
  
  digitalWrite(7, HIGH);

}

void loop() {    
  unsigned long TempoAtual = millis();
  
  if (TempoAtual - TempoAnterior == 4000 && digitalRead(7) == HIGH) {
  
  TempoAnterior = TempoAtual;
    
  digitalWrite(13, HIGH);
    
  digitalWrite(7, LOW);
  }
  
  if (TempoAtual - TempoAnterior == 6000 && digitalRead(13) == HIGH) {
  
  TempoAnterior = TempoAtual;
  
  digitalWrite(8, HIGH);
    
  digitalWrite(13, LOW);
  }
  
  if (TempoAtual - TempoAnterior == 2000 && digitalRead(8) == HIGH) {
  
  TempoAnterior = TempoAtual;
    
  digitalWrite(7, HIGH);
    
  digitalWrite(8, LOW);
  }
};
```

## 🚀 Como Executar

### Passo 1: Preparação do Hardware
1. Monte o circuito conforme o diagrama acima
2. Conecte o Arduino ao computador via cabo USB
3. Verifique se todas as conexões estão corretas

### Passo 2: Upload do Código
1. Abra a Arduino IDE
2. Abra o arquivo `.ino` do projeto
3. Selecione a placa correta em **Ferramentas > Placa**
4. Selecione a porta COM correta em **Ferramentas > Porta**
5. Clique em **Upload** (ou pressione Ctrl+U)

### Passo 3: Execução
1. Aguarde o upload finalizar
2. O semáforo deve começar a funcionar automaticamente
3. Observe a sequência: Verde → Amarelo → Vermelho

---

## Tabela de Avaliação entre Pares

### Avaliador: Felipe Neves

|Critério|	Contempla (Pontos)|	Contempla Parcialmente (Pontos)	|Não Contempla (Pontos)	|Observações do Avaliador|
|-|-|-|-|-|
|Montagem física com cores corretas, boa disposição dos fios e uso adequado de resistores	|Até 3	|Até 1,5	|0 |3 |	
|Temporização adequada conforme tempos medidos com auxílio de algum instrumento externo	|Até 3	|Até 1,5	|0 |3 |	
|Código implementa corretamente as fases do semáforo e estrutura do código (variáveis representativas e comentários) |	Até 3|	Até 1,5 |	0 |3 |	
|Ir além: Implementou um componente de extra, fez com millis() ao invés do delay() e/ou usou ponteiros no código |	Até 1 |	Até 0,5 |	0 |3 |	
| |10| | |Pontuação Total|

Contemplou os pontos de maneira eficiente e lógica.

### Avaliador: Leandro Filho

|Critério|	Contempla (Pontos)|	Contempla Parcialmente (Pontos)	|Não Contempla (Pontos)	|Observações do Avaliador|
|-|-|-|-|-|
|Montagem física com cores corretas, boa disposição dos fios e uso adequado de resistores	|Até 3	|Até 1,5	|0 |3 |
|Temporização adequada conforme tempos medidos com auxílio de algum instrumento externo	|Até 3	|Até 1,5	|0 |3 |	
|Código implementa corretamente as fases do semáforo e estrutura do código (variáveis representativas e comentários) |	Até 3|	Até 1,5 |	0 |3 |	
|Ir além: Implementou um componente de extra, fez com millis() ao invés do delay() e/ou usou ponteiros no código |	Até 1 |	Até 0,5 |	0 |3 |	
| |10| | |Pontuação Total|

Contemplou os pontos de maneira eficiente e lógica.