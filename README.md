# Projeto de Controle de LEDs com Botão no Raspberry Pi Pico 🎮💡

## 📋 Tabela de Conteúdos
- [📌 Introdução](#-introdução)
- [🛠️ Componentes Necessários](#-componentes-necessários)
- [🔧 Configuração do Hardware](#-configuração-do-hardware)
- [💻 Código Fonte](#-código-fonte)
- [🚀 Funcionamento do Código](#-funcionamento-do-código)

## 📌 Introdução
Este projeto utiliza um Raspberry Pi Pico para controlar três LEDs (azul, vermelho e verde) com um botão. Quando o botão é pressionado, os LEDs são acesos e desligados em sequência após intervalos de tempo específicos. O código foi desenvolvido em C utilizando a SDK do Raspberry Pi Pico.

## 🛠️ Componentes Necessários
- 🖥️ Raspberry Pi Pico
- 🔵 LED Azul
- 🔴 LED Vermelho
- 🟢 LED Verde
- 🔘 Botão
- 🔌 Resistores (330Ω para os LEDs)


## 💻 Código Fonte
O código fonte está disponível no arquivo `main.c`. Ele utiliza as bibliotecas padrão do Raspberry Pi Pico para controlar os GPIOs e gerenciar temporizadores.

### Estrutura do Código
- **Inicialização**:
  - Configura os pinos dos LEDs como saídas.
  - Configura o pino do botão como entrada com pull-up interno.

- **Loop Principal**:
  - Verifica o estado do botão.
  - Se o botão for pressionado, acende os LEDs e agenda alarmes para desligá-los após 3, 6 e 9 segundos, respectivamente.

- **Callbacks**:
  - Funções `turn_off_blue_callback`, `turn_off_red_callback`, e `turn_off_green_callback` são chamadas pelos alarmes para desligar os LEDs.

## 🚀 Funcionamento do Código
1. **Inicialização**:
   - O programa configura os pinos dos LEDs como saídas e o pino do botão como entrada com pull-up.

2. **Leitura do Botão**:
   - O loop principal verifica continuamente o estado do botão.
   - Se o botão for pressionado, os LEDs são acesos.

3. **Temporização**:
   - Após o botão ser pressionado, alarmes são configurados para desligar os LEDs após 3, 6 e 9 segundos.

4. **Callbacks**:
   - Quando os alarmes expiram, as funções de callback desligam os LEDs e atualizam o estado `led_active`.
   ---