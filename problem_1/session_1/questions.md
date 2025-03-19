# Questões:
### 1. Como criar memórias e acessar na FPGA

Em FPGAs, as memórias são criadas utilizando os recursos internos disponíveis, que geralmente se dividem em:

- Block RAM (BRAM): São blocos de memória dedicados presentes no chip, ideais para armazenar grandes quantidades de dados ou instruções. Você pode instanciá-los diretamente em Verilog utilizando os componentes e primitives fornecidos pelo fabricante.  
- Distributed RAM: Utiliza LUTs (Look-Up Tables) configuradas como pequenas unidades de memória, geralmente para armazenamento de dados menores ou buffers rápidos.

O acesso a essas memórias é feito através de sinais de controle (como clock, enable, write/read).

---

### 2. Quantas instruções?

1. adição
2. adição de matriz
3. subtração 
4. subtração de matriz
5. multiplicação
6. multiplicação de matriz
7. swap
8. transposição de matriz
9. determinante de matriz
10. multiplicação de matriz por escalar
11. calcular matriz oposta
12. leitura 
13. escrita

13 instruções

### 3. Qual o tamanho das instruções?

32 bits

### 4. Quais limitantes das instruções?

As limitações das instruções geralmente decorrem de:
- Número de bits diOs principais limitantes do tamanho das instruções de máquina são número de bits disponíveis (para opcode, operandos e endereços), complexidade do decodificador, eficiência do pipeline, recursos de hardware (uso de memória e consumo de energia) e compatibilidade da arquitetura (expansibilidade e suporte a versões anteriores).

---

### 5. O que é ISA?

ISA (Instruction Set Architecture) é o conjunto de especificações que define:
- O conjunto de instruções: Quais operações o processador pode realizar (aritméticas, lógicas, de controle, etc.).
- Os registradores disponíveis: Incluindo o tamanho e a quantidade.
- Os modos de endereçamento: Formas de acessar os operandos.
- O formato das instruções: Como os bits são organizados para representar operações e operandos.

Em resumo, a ISA estabelece a “linguagem” que conecta o software (compiladores, sistemas operacionais, aplicações) ao hardware do processador.

---

### 6. O que é datapath?

O datapath é o conjunto de componentes de hardware responsáveis pelo processamento dos dados dentro do processador. Ele engloba:
- Unidade Lógica Aritmética (ALU): Realiza operações aritméticas e lógicas.
- Registradores: Armazenam dados temporários e resultados intermediários.
- Barras e multiplexadores: Direcionam o fluxo dos dados entre os componentes.
- Interconexões com a memória: Para a leitura e escrita dos dados.

Basicamente, o datapath executa as instruções definidas pela ISA, realizando as operações efetivas sobre os dados e interligando os diversos módulos do processador.
