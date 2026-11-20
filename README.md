# AVA3 — Situação 2: Placa 2 (2 Botões e 2 LEDs — Módulo Transceptor 2)

Código-fonte referente à **Placa 2** na **Situação 2** (expansão para comunicação serial bidirecional entre duas placas Arduino Uno no **Tinkercad Circuits**, com dois botões e dois LEDs no conjunto)[cite: 2].

## Arquivo Principal
- `Placa 2_dois_led_dois_botao.txt`

## Visão Geral do Circuito e Funcionamento
- **Microcontrolador:** Arduino Uno (Placa 2 — transceptora, à direita na simulação)[cite: 2].
- **Entrada local (`BOT2`):** botão (*push button*) no pino `6` (`INPUT_PULLUP`) referenciado ao `GND`, enviando `!digitalRead(BOT2)` por `Serial.write()` a cada `500 ms` (`delay(500)`) a `9600` bps[cite: 2].
- **Saída local (`LED1`):** LED vermelho no pino `A0` (`OUTPUT`) com resistor limitador de corrente e `GND` comum, controlado por `digitalWrite(LED1, dados)` conforme bytes lidos via `Serial.available()` e `Serial.read()`[cite: 2].
- **Interligação:** conexões UART cruzadas (`TX` $\rightarrow$ `RX` e `RX` $\rightarrow$ `TX`) e referência de terra (`GND`) comum entre os microcontroladores[cite: 2].

## Cenários Documentados no Tinkercad
- **Sistema na Situação 2 com dois botões e dois LEDs desligados:** repouso inicial com ambos os botões soltos e os dois LEDs apagados[cite: 2].
- **Sistema na Situação 2 com dois botões e o LED da placa 1 ligado:** acionamento de `BOT2` na placa 2 envia o comando pela interface serial e acende `LED2` na placa 1.
- **Sistema na Situação 2 com dois botões e o LED da placa 2 ligado:** acionamento de `BOT1` na placa 1 envia o sinal pela interface serial e acende `LED1` na placa 2.
