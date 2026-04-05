# Anotações sobre "Conceitos Introdutórios"

## Aula CS50 - 2024 Version

**OBS: Ironicamente não fiz muitas anotações exclusivamente sobre o Scratch, mas sim sobre a lógica por trás de alguns conceitos introdutórios passados na aula.**

> "Learn to be confortable with the uncomfortable! (and learn how to  learn programming!)"

### 1. O que é Ciência da Computação?
- Pensamento Computacional
	- Resolução de problemas de forma mais metódica, clara e precisa;
	- Limpar o processo de pensamento;

![ImageIdeia1|452](https://cs50.harvard.edu/college/2020/spring/notes/0/input_output.png)

Input: Ex: Problema
Inside the Square: Processo / Algoritmos / Códigos
Output: Ex: Objetivo (Solução)

--------
### 2. Binary Digit (0 and 1):
- **1 Byte = ** 8 bits (Dígitos Binários)
- **Linguagem de máquina:** descreve as coisas através de diferentes permutações de números (representar informações com 0's e 1's);

Exemplo de Representação:
![BinaryRepresentation|471](https://www.virtualcuriosities.com/wp-content/uploads/2023/11/bits-as-lamps.webp)


#### Uma sequência de bites pode representar:
- Números Naturais (Notação Binária)
- Números Inteiros (Notação Complemento de dois)
- Letras (ASCII, Unicode, etc...)


**OBS: Notação**
- Binária: Base 2
- Octal: Base 8
- Decimal: Base 10
- Hexadecimal: Base 16

-----------
### 3. Código ASCII (American Standard Code for Information Interchange)
- Representação de caracteres através de números binários.

![ASCII|563](https://linuxhandbook.com/content/images/2023/01/2.png)
- **Tamanho:** Originalmente **8 bits** (128 caracteres - 0 a 127 ). Na prática, ocupa 1 byte, com o primeiro bit sendo `0`.
- **Intervalos Importantes:**
    - **Números (0-9):** 48 a 57.
    - **Letras Maiúsculas (A-Z):** 65 a 90.
    - **Letras Minúsculas (a-z):** 97 a 122.
        
- **Curiosidade CS50:** A diferença entre 'A' (65) e 'a' (97) é exatamente $2^5$ (32). No binário, isso significa que apenas um bit muda de posição para alternar entre maiúscula e minúscula.
- **Limitação:** Não suporta acentuação ou emojis (resolvido posteriormente pelo Unicode/UTF-8).

**Importância:** 
- **Economia antiga:** Antigamente, esse 8º bit "vazio" era usado para _checksum_ (verificar se o dado não corrompeu no caminho).
- **Extensões:** Quando precisaram de acentos (como o nosso `á`, `õ`, `ç`), criaram o **Extended ASCII**. Aí sim passaram a usar o 8º bit, permitindo mais 128 caracteres (totalizando 256).
- **Unicode (UTF-8):** Hoje usamos o Unicode. O UTF-8 é brilhante porque ele é "retrocompatível": se o primeiro bit é `0`, ele lê como ASCII de 7 bits. Se o primeiro bit for `1`, ele entende que precisa de mais bytes para formar aquele caractere (como um emoji 💡).

-------------
### 4. Código Unicode 
- Pode usar até 32 bits (ou mais).
- Tipos:
	- UTF-8 (1 byte)
	- UTF-16 (2 bytes)
	- UTF-32 (4 bytes)
	- Etc...
- Permite a representação de caracteres como acentos, emojis e até mesmo diferentes alfabetos de diferentes idiomas.
- **OBS:** O Unicode usa binário, mas ele usa **sinalizadores** nos bits para avisar o computador que diferentes bytes podem fazer parte de um "mesmo todo". 

 **Exemplo prático:**
 ```c
  **ASCII:** `01000001` (Sempre 8 bits = Letra A)
      
 **Unicode (via UTF-8):** > * Pode ser `01000001` (A)
 
Pode ser `11110000 10011111 10011000 10000010` (Isso tudo junto é um único emoji 🚀).
 ```
Exemplo de Representação: U+1F602 (Base 16)

- **Modificadores (Combinações):**
	- Usam mais bits e Unicodes para dar características específicas a um emoji (por exemplo).
	- Ex: U+1F44D (Emoji de Joaninha padrão)
	- U+1F44D U+1F3FD (Emoji de Joaninha com uma tonalidade de cor diferente)
------------
### 5. RGB (Red, Green, Blue) - Sistema Hexadecimal (Hex):
(Continuar Anotando)