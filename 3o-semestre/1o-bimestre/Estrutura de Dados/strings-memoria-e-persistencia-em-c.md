# Strings, Memória e Persistência em C

## 1. Cadeia de caracteres (strings em C)

- **Definição:** Uma string em C é uma sequência contínua de caracteres do tipo `char`, encerrada por um caractere nulo (`'\0'`).
- **Armazenamento:** Permite armazenar e manipular sequências de texto na memória RAM.

**Exemplo de código:**

```c
char saudacao[] = "Olá, Mundo!";
printf("%s\n", saudacao);
```

---

## 2. Manipulação manual

- **Definição:** Consiste na implementação direta de rotinas clássicas de texto, como cálculo de tamanho, cópia e comparação de strings.
- **Funcionamento:** É feita pela varredura com ponteiros, sem o auxílio de funções prontas da biblioteca padrão.

---

## 3. Alocação de memória (stack × heap)

**Definição:** A memória usada pelo programa inclui regiões com formas distintas de alocação, como a **pilha (*stack*)** e o **monte (*heap*)**:

- **Pilha (*stack*):** Espaço de alocação automática, rápida e com duração ligada ao escopo de execução. A alocação das variáveis locais ocorre automaticamente.
- **Monte (*heap*):** Espaço flexível para alocação dinâmica, gerido pelo programador por meio de ponteiros. Em C, pode-se alocar memória com `malloc`.

---

## 4. Persistência de dados em linguagem C (texto e binário)

- **Definição:** Mecanismo para transferir dados da memória RAM volátil para armazenamento persistente em disco, em formato de texto ou binário.

> **Conteúdo pendente:** O trecho enviado sobre as estruturas utilizadas foi interrompido após “Utiliza a biblioteca padrão `”.

---
