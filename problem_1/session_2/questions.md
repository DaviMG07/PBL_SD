## O que o co-processador faz ao receber a instrução de 32 bits?(qual a primeira coisa que ele faz?)
  Ao receber a instrução, o co‐processador primeiro “busca” (carrega) os 32 bits para seu registrador interno e os decodifica – isto é, ele analisa o opcode e os campos de operandos para determinar qual operação executar.

Em outras palavras, o primeiro passo é a etapa de busca/decodificação: ele lê a instrução, incrementa o contador de programa (para apontar para a próxima) e interpreta seus bits para saber como proceder na execução.

## Como funciona a ULA?
  A ULA é um circuito digital que, sem usar memória interna, processa em tempo real os dados que recebe, realizando operações aritméticas (como soma e subtração) e lógicas (como AND, OR e XOR). Ela recebe os operandos e um código de operação (sinais de controle) que determinam a função a ser executada e, após o processamento, fornece o resultado e sinais de status (como zero ou carry) para orientar o próximo passo da CPU.

## Quanto tempo a memória vai precisar para escrita?
  Para o controlador SDRAM, que opera em 100MHZ, o período de clock é de 10ns, ou seja, a memória SDRAM leva em torno de 10ns para realizar operação de escrita.

## Referencias:
PATTERSON, David A.; HENNESSY, John L. Computer Organization and Design: ARM Edition. 8. ed. Burlington: Morgan Kaufmann, 2017.
TERASIC. DE1-SoC Development Kit. Terasic. Disponível em: https://www.terasic.com.tw/cgi-bin/page/archive.pl?Language=English&CategoryNo=165&No=836#contents. Acesso em: 12 mar. 2025.

