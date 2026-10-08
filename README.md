# 🎹 Raspberry Synth

> Sintetizador digital desenvolvido em **C++** sobre **Raspberry Pi**, com controles físicos, geração de áudio em tempo real, conversão digital-analógica, amplificação e reprodução sonora.

[![C++](https://img.shields.io/badge/C%2B%2B-17%2B-blue.svg)](https://isocpp.org/)
[![Raspberry Pi](https://img.shields.io/badge/Raspberry%20Pi-Embedded-C51A4A.svg)](https://www.raspberrypi.com/)
[![CMake](https://img.shields.io/badge/CMake-Build-064F8C.svg)](https://cmake.org/)
[![Git](https://img.shields.io/badge/Git-Version%20Control-F05032.svg)](https://git-scm.com/)

---

# 📑 Sumário

- [Sobre o projeto](#-sobre-o-projeto)
- [Objetivos](#-objetivos)
- [Escopo](#-escopo)
- [Funcionalidades](#-funcionalidades)
- [Requisitos funcionais](#-requisitos-funcionais)
- [Requisitos não funcionais](#-requisitos-não-funcionais)
- [Tecnologias](#-tecnologias)
- [Infraestrutura](#-infraestrutura)
  - [Raspberry Pi](#-raspberry-pi)
  - [GPIO](#-gpio)
  - [Níveis lógicos](#-níveis-lógicos)
  - [Alimentação elétrica](#-alimentação-elétrica)
  - [Interfaces de comunicação](#-interfaces-de-comunicação)
  - [SPI](#-spi)
  - [I²C](#-i²c)
  - [I²S](#-i²s)
  - [ADC](#-adc)
  - [DAC](#-dac)
  - [Botões](#-botões)
  - [Potenciômetros](#-potenciômetros)
  - [Amplificador](#-amplificador)
  - [Alto-falante](#-alto-falante)
  - [P2](#-conexão-p2)
- [Servidor e sistema](#-servidor-e-sistema)
- [Arquitetura do sistema](#-arquitetura-do-sistema)
- [Arquitetura de software](#-arquitetura-de-software)
- [Síntese de áudio](#-síntese-de-áudio)
- [Notas musicais](#-notas-musicais)
- [Estrutura do projeto](#-estrutura-do-projeto)
- [Instalação](#-instalação)
- [Configuração do Raspberry Pi](#-configuração-do-raspberry-pi)
- [Montagem eletrônica](#-montagem-eletrônica)
- [Testes](#-testes)
- [Etapas de desenvolvimento](#-etapas-de-desenvolvimento)
- [Problemas e soluções](#-problemas-e-soluções)
- [Equipe](#-equipe)
- [Licença](#-licença)
- [Status](#-status)

---

# 📌 Sobre o projeto

O **Raspberry Synth** é um projeto acadêmico de desenvolvimento de um **sintetizador digital embarcado**, utilizando um Raspberry Pi como unidade principal de processamento e C++ como linguagem de programação.

O objetivo é construir um equipamento capaz de receber comandos físicos do usuário, gerar sinais de áudio digitalmente, processá-los e encaminhá-los para um sistema de amplificação e reprodução sonora.

O projeto integra conceitos de:

- Programação em C++;
- Programação orientada a objetos;
- Sistemas embarcados;
- Eletrônica digital;
- Eletrônica analógica;
- Processamento digital de sinais;
- Síntese sonora;
- Comunicação entre periféricos;
- Sistemas Linux;
- Áudio digital;
- Controle de hardware;
- Engenharia de software.

---

# 🎯 Objetivos

## Objetivo geral

Desenvolver um sintetizador digital funcional utilizando um **Raspberry Pi** e **C++**, capaz de gerar, processar, amplificar e reproduzir sinais de áudio correspondentes a diferentes notas musicais.

## Objetivos específicos

- Implementar a geração digital de ondas sonoras;
- Desenvolver uma arquitetura de software modular;
- Criar um sistema de entrada através de botões físicos;
- Implementar controles através de potenciômetros;
- Realizar a leitura de entradas digitais e analógicas;
- Integrar um ADC ao Raspberry Pi;
- Integrar um DAC ou interface de áudio;
- Implementar processamento de áudio em tempo real;
- Integrar um amplificador;
- Reproduzir o áudio através de um alto-falante;
- Avaliar latência e desempenho;
- Documentar hardware e software;
- Criar uma base que permita futuras expansões.

---

# 🔭 Escopo

A primeira versão do Raspberry Synth terá como foco a implementação de um sintetizador simples e funcional.

### Escopo inicial

```text
12 botões
    ↓
Seleção de nota
    ↓
Raspberry Pi
    ↓
Motor de síntese C++
    ↓
DAC / Interface de áudio
    ↓
P2
    ↓
Amplificador
    ↓
Alto-falante
```

O sistema inicialmente trabalhará com uma oitava cromática composta por 12 notas:

**C, C#, D, D#, E, F, F#, G, G#, A, A# e B.**

---

# 🎹 Funcionalidades

## Primeira versão

- [ ] Geração de onda senoidal;
- [ ] Geração de onda quadrada;
- [ ] Geração de onda triangular;
- [ ] Geração de onda dente de serra;
- [ ] Reprodução de 12 notas;
- [ ] Leitura dos 12 botões;
- [ ] Controle de volume;
- [ ] Controle de parâmetro de síntese;
- [ ] Saída de áudio;
- [ ] Amplificação;
- [ ] Reprodução através de alto-falante.

## Funcionalidades futuras

- [ ] Envelope ADSR;
- [ ] Filtro passa-baixa;
- [ ] Filtro passa-alta;
- [ ] LFO;
- [ ] Vibrato;
- [ ] Portamento;
- [ ] Polifonia;
- [ ] MIDI;
- [ ] Display;
- [ ] Presets;
- [ ] Gravação;
- [ ] Interface gráfica;
- [ ] Mais oitavas;
- [ ] Efeitos de áudio.

---

# 📋 Requisitos funcionais

### RF01 — Geração de áudio

O sistema deverá gerar digitalmente sinais correspondentes às formas de onda implementadas.

### RF02 — Seleção de notas

O sistema deverá permitir que o usuário selecione notas através dos botões físicos.

### RF03 — Processamento

O sistema deverá processar os sinais de áudio antes da saída.

### RF04 — Controle de parâmetros

O usuário deverá conseguir modificar parâmetros do sintetizador através dos potenciômetros.

### RF05 — Conversão digital-analógica

O sistema deverá converter os samples digitais em sinal analógico através de um DAC ou interface de áudio compatível.

### RF06 — Amplificação

O sinal analógico deverá ser encaminhado para um amplificador adequado.

### RF07 — Reprodução

O sistema deverá reproduzir o áudio através de um alto-falante.

### RF08 — Operação contínua

O sistema deverá permanecer em execução enquanto o sintetizador estiver sendo utilizado.

---

# ⚙️ Requisitos não funcionais

### RNF01 — Desempenho

O sistema deverá apresentar latência suficientemente baixa para permitir interação musical.

### RNF02 — Estabilidade

A aplicação deverá funcionar continuamente sem travamentos durante a utilização normal.

### RNF03 — Modularidade

O software deverá ser dividido em componentes independentes.

### RNF04 — Manutenibilidade

O código deverá possuir organização e nomenclatura que facilitem manutenção e expansão.

### RNF05 — Segurança

O sistema deverá respeitar os limites elétricos dos GPIOs e dos demais componentes.

### RNF06 — Portabilidade

O código deverá ser preparado para execução em Raspberry Pi utilizando Linux.

### RNF07 — Documentação

As decisões de hardware, software, testes e arquitetura deverão ser documentadas.

---

# 🛠️ Tecnologias

## Software

| Tecnologia | Utilização |
|---|---|
| C++ | Linguagem principal |
| CMake | Sistema de build |
| GCC/G++ | Compilador |
| Linux | Sistema operacional |
| Git | Controle de versão |
| GitHub | Repositório |
| VS Code | Ambiente de desenvolvimento |

## Hardware

| Componente | Função |
|---|---|
| Raspberry Pi | Processamento |
| ADC | Conversão analógico-digital |
| MCP3008* | Leitura dos potenciômetros |
| DAC / Interface de áudio | Conversão digital-analógica |
| Potenciômetros | Controle de parâmetros |
| Botões | Entrada das notas |
| Amplificador | Amplificação |
| Alto-falante | Reprodução |
| Cabos P2 | Transporte do sinal de áudio |

> \* O MCP3008 é uma proposta inicial e poderá ser substituído dependendo da arquitetura final.

---

# 🖥️ Infraestrutura

A infraestrutura do Raspberry Synth é dividida em quatro camadas:

```text
┌──────────────────────────────────────┐
│           CAMADA DE SOFTWARE         │
│                                      │
│          Aplicação C++               │
│          Motor de síntese            │
└──────────────────┬───────────────────┘
                   │
┌──────────────────▼───────────────────┐
│         CAMADA DE HARDWARE            │
│                                      │
│ GPIO / SPI / I²C / I²S / USB         │
└──────────────────┬───────────────────┘
                   │
┌──────────────────▼───────────────────┐
│          CAMADA DE ÁUDIO              │
│                                      │
│ DAC → P2 → Amplificador               │
└──────────────────┬───────────────────┘
                   │
┌──────────────────▼───────────────────┐
│          CAMADA DE SAÍDA              │
│                                      │
│             Alto-falante             │
└──────────────────────────────────────┘
```

---

# 🍓 Raspberry Pi

O Raspberry Pi será o **computador embarcado principal** do projeto.

Ele será responsável por executar o sistema operacional, o programa em C++ e a comunicação com os periféricos.

### Responsabilidades

- Executar o sistema operacional;
- Executar a aplicação C++;
- Gerenciar memória e CPU;
- Ler os botões;
- Ler os potenciômetros;
- Processar os parâmetros;
- Gerar samples;
- Enviar áudio ao dispositivo de saída;
- Gerenciar periféricos;
- Disponibilizar rede para desenvolvimento;
- Registrar informações e logs.

### Modelo

O modelo definitivo deverá ser definido pela equipe.

**Raspberry Pi 4** e **Raspberry Pi 5** são candidatos adequados devido ao desempenho disponível para processamento de áudio.

---

# 🔌 GPIO — General Purpose Input/Output

Os **GPIOs** são pinos de entrada e saída utilizados para comunicação direta entre o Raspberry Pi e circuitos eletrônicos.

No Raspberry Synth, eles serão utilizados principalmente para detectar os botões.

```text
                 RASPBERRY PI
                      │
        ┌─────────────┼──────────────┐
        │             │              │
       GPIO          GPIO           GPIO
        │             │              │
        ▼             ▼              ▼
      Botão C       Botão D        Botão E
```

Quando o usuário pressionar um botão, o estado elétrico do GPIO será alterado e o software poderá detectar esse evento.

---

# ⚡ Níveis lógicos

Os GPIOs do Raspberry Pi utilizam lógica de **3,3 V**.

```text
0 V     → LOW  → 0 lógico
3,3 V   → HIGH → 1 lógico
```

**5 V não deve ser aplicado diretamente aos GPIOs.**

Essa é uma das principais regras elétricas do projeto.

---

# 🔢 GPIO como entrada

Os GPIOs configurados como entrada permitem que o Raspberry Pi leia o estado de componentes externos.

Exemplo utilizando pull-up:

```text
        3,3 V
          │
       Pull-up
          │
          ├──────── GPIO
          │
       [ BOTÃO ]
          │
         GND
```

Interpretação:

```text
Botão aberto     → HIGH
Botão pressionado → LOW
```

O software deverá utilizar uma estratégia adequada de **debounce** para evitar múltiplas leituras provocadas pelo ruído mecânico do botão.

---

# 📤 GPIO como saída

Um GPIO configurado como saída permite que o Raspberry Pi controle um sinal digital.

```text
Raspberry Pi
     │
    GPIO
     │
     ▼
   Circuito
```

No Raspberry Synth, GPIOs de saída poderão ser utilizados futuramente para LEDs indicadores, displays ou outros componentes.

---

# 🧩 Mapeamento inicial dos GPIOs

O mapeamento abaixo é apenas uma proposta:

| Função | GPIO | Direção |
|---|---:|---|
| Botão C | GPIO 17 | Entrada |
| Botão C# | GPIO 18 | Entrada |
| Botão D | GPIO 27 | Entrada |
| Botão D# | GPIO 22 | Entrada |
| Botão E | GPIO 23 | Entrada |
| Botão F | GPIO 24 | Entrada |
| Botão F# | GPIO 25 | Entrada |
| Botão G | GPIO 5 | Entrada |
| Botão G# | GPIO 6 | Entrada |
| Botão A | GPIO 12 | Entrada |
| Botão A# | GPIO 13 | Entrada |
| Botão B | GPIO 16 | Entrada |

> **Atenção:** esse mapeamento não é definitivo. Os GPIOs finais deverão ser escolhidos considerando os barramentos SPI, I²C, I²S, alimentação e possíveis conflitos de hardware.

---

# 🔋 Alimentação elétrica

A alimentação será uma parte crítica da infraestrutura.

O Raspberry Pi, o amplificador, o DAC, o ADC e demais componentes deverão receber tensões compatíveis com suas especificações.

Uma arquitetura possível será:

```text
                 FONTE
                   │
          ┌────────┴────────┐
          │                 │
          ▼                 ▼
    Raspberry Pi       Amplificador
          │
     ┌────┴─────┐
     │          │
    ADC        DAC
```

### Regras

- Não alimentar componentes sem verificar sua tensão nominal;
- Não utilizar GPIO como fonte de alimentação de cargas de potência;
- Não alimentar o alto-falante diretamente pelo Raspberry Pi;
- Verificar corrente máxima das fontes;
- Garantir GND comum entre circuitos que compartilham sinais;
- Separar, quando necessário, alimentação de potência e sinais de áudio.

---

# 🔄 Interfaces de comunicação

O Raspberry Pi possui diversos protocolos que podem ser utilizados para conectar periféricos.

```text
┌────────────────────────────────────────┐
│              RASPBERRY PI              │
│                                        │
│ GPIO ───────────────► Botões           │
│                                        │
│ SPI ─────────────────► ADC             │
│                                        │
│ I²C ─────────────────► Expansores      │
│                                        │
│ I²S ─────────────────► Áudio           │
│                                        │
│ USB ─────────────────► Interface áudio │
└────────────────────────────────────────┘
```

---

# 🔌 SPI

**SPI (Serial Peripheral Interface)** é um protocolo de comunicação serial utilizado para comunicação rápida entre o Raspberry Pi e periféricos.

No projeto, poderá ser utilizado para o MCP3008.

### MCP3008

O MCP3008 possui:

- 8 entradas analógicas;
- Resolução de 10 bits;
- Comunicação SPI.

Fluxo:

```text
Potenciômetro
      │
      ▼
    MCP3008
      │
      │ SPI
      ▼
Raspberry Pi
      │
      ▼
     C++
```

---

# 🔗 I²C

O **I²C** utiliza duas linhas principais:

```text
SDA → Dados
SCL → Clock
```

Poderá ser utilizado futuramente para:

- Displays;
- Expansores de GPIO;
- Sensores;
- Controladores;
- Outros periféricos.

Caso o projeto aumente a quantidade de entradas, um expansor como o MCP23017 poderá reduzir a quantidade de GPIOs necessários.

---

# 🎵 I²S

O **I²S** é um protocolo destinado especificamente à transmissão de áudio digital.

É uma das interfaces mais importantes para uma possível arquitetura de áudio dedicada.

```text
C++
 │
 ▼
Motor de síntese
 │
 ▼
Samples digitais
 │
 ▼
I²S
 │
 ▼
DAC
 │
 ▼
Sinal analógico
 │
 ▼
Amplificador
 │
 ▼
Alto-falante
```

---

# 🎛️ ADC — Conversor Analógico-Digital

Os potenciômetros produzem uma tensão variável, enquanto o software trabalha com valores numéricos.

O ADC realiza a conversão:

```text
Tensão analógica
       │
       ▼
      ADC
       │
       ▼
Valor digital
       │
       ▼
     C++
```

Para um ADC de 10 bits:

```text
0 V       → 0
1,65 V    → aproximadamente 512
3,3 V     → 1023
```

O C++ poderá transformar esse valor em parâmetros do sintetizador.

---

# 🎚️ Potenciômetros

Os potenciômetros funcionarão como controles físicos.

Exemplo inicial:

```text
Potenciômetro 1
      │
      ▼
    Volume

Potenciômetro 2
      │
      ▼
Filtro / Timbre
```

A função definitiva do segundo potenciômetro será determinada durante os testes.

---

# 🔘 Sistema de botões

Os 12 botões representam uma oitava cromática.

```text
       C#   D#       F#   G#   A#
       │    │        │    │    │
       ▼    ▼        ▼    ▼    ▼

       C    D    E    F    G    A    B
```

Cada botão será associado a uma frequência.

O fluxo lógico será:

```text
Botão pressionado
       ↓
GPIO detecta LOW/HIGH
       ↓
Button
       ↓
Identificação da nota
       ↓
Note
       ↓
Frequência
       ↓
Oscillator
       ↓
Sample de áudio
```

---

# 🔊 DAC — Conversor Digital-Analógico

O DAC converte os samples digitais produzidos pelo sintetizador em um sinal analógico.

```text
C++
 │
 ▼
Sample digital
 │
 ▼
DAC
 │
 ▼
Sinal analógico
```

Essa etapa permite que o sinal seja posteriormente enviado para uma entrada de áudio.

---

# 🔊 Amplificador

O sinal proveniente do DAC é um sinal de áudio de baixa potência.

O amplificador aumenta sua capacidade de fornecer potência ao alto-falante.

```text
DAC
 │
 │ Sinal de linha
 ▼
Amplificador
 │
 │ Sinal de potência
 ▼
Alto-falante
```

O amplificador deverá ser selecionado de acordo com:

- Tensão disponível;
- Potência;
- Impedância;
- Tipo de entrada;
- Relação sinal/ruído;
- Dimensões;
- Dissipação térmica.

---

# 🔈 Alto-falante

O alto-falante converte o sinal elétrico em energia acústica.

```text
Sinal elétrico
      │
      ▼
┌──────────────┐
│ Alto-falante │
└──────┬───────┘
       │
       ▼
      🔊
     Áudio
```

Caso seja utilizado um alto-falante passivo, ele deverá ser ligado à saída de potência do amplificador.

---

# 🎧 Conexão P2

A conexão P2 poderá ser utilizada entre a saída analógica do sistema de áudio e a entrada do amplificador.

```text
DAC / Interface de áudio
          │
          │ P2
          ▼
     Amplificador
          │
          ▼
      Alto-falante
```

O P2 transporta **sinal de áudio**, não sendo utilizado para transportar a potência destinada ao alto-falante passivo.

---

# 🖥️ Servidor e sistema

O Raspberry Pi será o **computador embarcado do sistema**.

A aplicação principal será executada localmente no dispositivo.

Não existe necessidade de um servidor web externo para a geração do áudio.

```text
┌─────────────────────────────────┐
│          RASPBERRY PI           │
│                                 │
│       Sistema operacional       │
│               │                 │
│          Aplicação C++          │
│               │                 │
│        Motor de síntese         │
│               │                 │
│     GPIO / SPI / I²S / USB      │
│               │                 │
│         Hardware físico         │
└─────────────────────────────────┘
```

---

# 🐧 Sistema operacional

O Raspberry Pi utilizará uma distribuição Linux compatível com o modelo escolhido.

O sistema operacional será responsável por:

- Gerenciamento de processos;
- Gerenciamento de memória;
- Gerenciamento de CPU;
- Drivers;
- Sistema de arquivos;
- Rede;
- Comunicação com periféricos;
- Execução da aplicação.

---

# ⚙️ Aplicação C++

A aplicação será executada diretamente no Raspberry Pi.

```text
Linux
 │
 ▼
Executável C++
 │
 ├── Synthesizer
 ├── Oscillator
 ├── Note
 ├── Button
 ├── Potentiometer
 └── AudioOutput
```

A aplicação será responsável pela lógica principal do sintetizador.

---

# 🌐 Rede

A rede será utilizada principalmente durante o desenvolvimento.

```text
┌─────────────────────┐
│ PC / Notebook       │
│                     │
│ VS Code             │
│ Git                 │
└──────────┬──────────┘
           │
       Wi-Fi / Ethernet
           │
           ▼
┌─────────────────────┐
│ Raspberry Pi        │
│                     │
│ Código C++          │
│ Aplicação           │
└─────────────────────┘
```

A conexão de rede não será necessária para o funcionamento normal do sintetizador depois que o sistema estiver configurado.

---

# 🔐 SSH

O SSH permitirá administrar o Raspberry Pi remotamente.

Exemplo:

```bash
ssh usuario@ip-do-raspberry
```

Através dele será possível:

- Executar comandos;
- Compilar o projeto;
- Instalar dependências;
- Executar
