# Documentação Técnica: Sensores e Transdutores para Arquitetura IoT
## Especificações Físicas, Princípio de Funcionamento, Pinout e Condicionamento de Sinal

> **Tema:** Transdutores e Sensores Industriais e Comerciais em Sistemas Embarcados e IoT  
> **Referência:** `Aula 3 - IoT - Sensores (parte 2).ppt`  
> **Finalidade:** Guia Técnico para Repositório GitHub (Hardware & Arquitetura)

---

## 1. Classificação Geral de Sensores e Transdutores
Um **sensor** converte uma grandeza física (luz, temperatura, pressão, campo magnético, concentração gasosa) em um sinal elétrico mensurável (tensão, corrente, resistência ou trem de pulsos digitais).

![Visão Geral dos Sensores IoT](Apostilas/Imagens_Sensores_IoT/slide_sensor_02.png)
![Classificação Analógica vs Digital](Apostilas/Imagens_Sensores_IoT/slide_sensor_05.png)

---

## 2. Sensores de Luminosidade (LDR - Light Dependent Resistor)
- **Princípio Físico:** Fotorresistência semicondutora (Sulfeto de Cádmio - CdS). A incidência de fótons excita elétrons para a banda de condução, reduzindo drasticamente a resistência interna.
- **Curva Característica:** Resistência no escuro ($R_{\text{dark}} > 1\text{ M}\Omega$) vs. Resistência sob luz intensa ($R_{\text{light}} < 1\text{ k}\Omega$).
- **Circuito de Interface:** Divisor de tensão com resistor de referência fixo ($10\text{ k}\Omega$) conectado à entrada ADC ($A_0$).

![Sensor LDR e Curva de Resposta](Apostilas/Imagens_Sensores_IoT/slide_sensor_10.png)

---

## 3. Sensores de Temperatura e Umidade (DHT11 / DHT22)
- **Princípio Físico:** Elemento resistivo de umidade com substrato polimérico higroscópico e termistor NTC para temperatura.
- **Protocolo de Comunicação:** Barramento digital proprietário de 1 fio (*Single-Wire Bus*), enviando 40 bits serializados com soma de verificação (*checksum*).
- **Faixas de Operação:**
  - **DHT11:** $0\text{ a }50\text{ }^\circ\text{C}$ ($\pm 2\text{ }^\circ\text{C}$), $20\text{ a }90\%\text{ UR}$ ($\pm 5\%$).
  - **DHT22 (AM2302):** $-40\text{ a }+80\text{ }^\circ\text{C}$ ($\pm 0.5\text{ }^\circ\text{C}$), $0\text{ a }100\%\text{ UR}$ ($\pm 2\%$).

![Sensor DHT11/DHT22](Apostilas/Imagens_Sensores_IoT/slide_sensor_15.png)

---

## 4. Sensor Ultrassônico de Distância (HC-SR04)
- **Princípio Físico:** Emissão de pulsos acústicos de alta frequência ($40\text{ kHz}$) e medição do tempo de vôo (*Time-of-Flight - ToF*) do eco refletido pelo obstáculo.
- **Equação de Distância:**
  $$d = \frac{\Delta t \times v_{\text{som}}}{2} = \frac{\Delta t \times 340\text{ m/s}}{2} = \frac{\Delta t\text{ (}\mu\text{s)}}{58}$$
- **Sinais:** Pulso de disparo *Trigger* ($\ge 10\text{ }\mu\text{s}$) e largura do pulso de retorno *Echo*.

![Sensor Ultrassônico HC-SR04](Apostilas/Imagens_Sensores_IoT/slide_sensor_22.png)

---

## 5. Sensores de Presença e Movimento (PIR - Passive Infrared)
- **Princípio Físico:** Elemento piroelétrico encapsulado com lente Fresnel que detecta variações na radiação infravermelha de comprimento de onda corporal ($pprox 9.4\text{ }\mu\text{m}$).
- **Interface:** Saída digital em nível alto ($3.3\text{V}$) com temporizador ajustável de retenção (*Delay Time*) e ajuste de sensibilidade.

![Sensor PIR](Apostilas/Imagens_Sensores_IoT/slide_sensor_30.png)

---

## 6. Sensores de Gases e Qualidade do Ar (Série MQ - MQ-2, MQ-135)
- **Princípio Físico:** Camada sensora de Dióxido de Estanho ($	ext{SnO}_2$) aquecida internamente. Em ar limpo, a condutividade é baixa; na presença de gases redutores (GPL, Metano, Álcool, Fumaça), a resistência decresce proporcionalmente à concentração em PPM.

![Sensores da Série MQ](Apostilas/Imagens_Sensores_IoT/slide_sensor_40.png)

---

## 7. Quadro Resumo de Especificações Técnicas

| Sensor / Módulo | Grandeza Medida | Tipo de Sinal | Tensão de Operação | Tempo de Resposta |
| :--- | :--- | :---: | :---: | :---: |
| **LDR** | Intensidade Luminosa (Lux) | Analógico ($V_{\text{out}}$) | $3,3\text{ V} - 5\text{ V}$ | $\approx 20\text{ ms}$ |
| **DHT22** | Temperatura / Umidade | Digital Serial (1 fio) | $3,3\text{ V} - 5\text{ V}$ | $2\text{ s}$ |
| **HC-SR04** | Distância ($2\text{ cm} - 400\text{ cm}$) | Pulso Digital (Echo) | $5\text{ V}$ | $60\text{ ms}$ |
| **PIR HC-SR501**| Movimento Térmico | Digital ($0 / 3,3\text{ V}$) | $4,5\text{ V} - 20\text{ V}$ | $0,3\text{ s} - 5\text{ min}$ |
| **MQ-2** | GLP, Fumaça, Metano | Analógico / Digital | $5\text{ V}$ (Aquecedor) | $\le 10\text{ s}$ |

---
*Documentação de hardware para engenharia de computação e arquitetura IoT.*
