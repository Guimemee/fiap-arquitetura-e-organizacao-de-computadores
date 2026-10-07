# GLOBAL SOLUTION 2022: ARQUITETURA E ORGANIZAÇÃO DE COMPUTADORES
## Enunciados Oficiais, Especificações de Projeto e Arquivos de Referência

> **Curso:** Engenharia de Computação (1ECB / 1ECR)  
> **Ano Letivo:** 2022  
> **Tema Geral:** Arquitetura de Computadores, Sistemas Embarcados IoT e Soluções Tecnológicas Integradas

---

## 1. Arquivos Oficiais Anexados
Nesta pasta encontram-se os documentos originais da Global Solution:
1. [`GS-1SEM-2022_1EC.pdf`](GS-1SEM-2022_1EC.pdf) - **Global Solution 1º Semestre 2022**
2. [`GS22_1EC.pptx`](GS22_1EC.pptx) - **Global Solution 2º Semestre 2022**

---

## 2. Enunciado e Diretrizes da Global Solution - 1º Semestre (2022)

### Proposta Técnica e Objetivos
O projeto desafia os alunos de Engenharia de Computação a estruturar um sistema computacional completo de monitoramento e automação industrial baseado na arquitetura **NodeMCU ESP8266 / Arduino** com protocolos de comunicação em rede.

### Requisitos e Especificações:
1. **Sensoriamento e Coleta de Dados:** Leitura periódica de grandezas ambientais (temperatura, luminosidade via ADC $A_0$ e presença via sensores digitais).
2. **Processamento e Decisão Local:** Lógica de conversão A/D, filtragem digital e acionamento de atuadores com lógica invertida.
3. **Transmissão via Protocolo MQTT:** Envio contínuo de telemetria para Broker MQTT (`iot.eclipse.org` ou `broker.hivemq.com`) em tópicos normatizados (`GS_1EC_Pub` e `GS_1EC_Sub`).
4. **Interface Web Local:** Servidor HTTP embarcado (*WebServer*) respondendo requisições com dados em tempo real.

---

## 3. Enunciado e Diretrizes da Global Solution - 2º Semestre (2022)

### Proposta Técnica e Objetivos
Consolidação dos conhecimentos em microarquitetura de computadores, hierarquia de memória e dimensionamento de desempenho computacional para veículos elétricos e cidades inteligentes.

### Tópicos Exigidos:
1. **Análise de Desempenho Arquitetural:** Cálculo de CPI médio, tempo de CPU e MIPS sob cargas de trabalho com instruções aritméticas, lógicas, desvios e acessos à memória.
2. **Hierarquia de Memória e AMAT:** Análise de latência de acesso à Cache L1, L2, Memória Principal DRAM e impacto do *Miss Penalty* no throughput do sistema.
3. **Barramentos e Comunicação de Periféricos:** Dimensionamento de largura de banda para barramentos PCI-Express e interfaces seriais de tempo real (SPI, I2C, CAN Bus automotivo).

---
*README compilado e validado para documentação de projetos no GitHub.*
