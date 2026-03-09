# Anotações sobre "Arrays (Vetores)"
## Aula CS50 - 2024 Version

![Compiling](https://cs50.harvard.edu/x/2022/notes/1/compiler.png)

---------
### Criptografia:
- A criptografia transforma dados legíveis (plaintext) em um formato codificado (ciphertext) por meio de algoritmos matemáticos e uma chave secreta, garantindo que apenas destinatários autorizados consigam reverter o processo para aceder à informação original. No contexto de programação em C, como visto no CS50, isto envolve manipular caracteres individualmente através dos seus valores na tabela ASCII, aplicando deslocamentos lógicos (como na Cifra de César) para mascarar o conteúdo original, protegendo assim a confidencialidade e a integridade dos dados em trânsito ou armazenamento.

----------
### Compilador:

```c
make hello
./hello
```
- O comando make na verdade é uma forma simplificada de rodar um compilador, como forma de evitar "line commands" e comandos extras. Em "C" ele é chamado de Clang.
```c
clang hello.c
./a.out
```

#### Command Line Arguments:
- São letras adicionais / "shortland notation"que você digita no prompt de comando que de alguma forma modifica o comportamento do programa.

- Para aceitar argumentos, a função main precisa ser declarada com dois parâmetros específicos:

```C
int main(int argc, string argv[])
```

- ***argc (Argument Count):*** Um inteiro que guarda a quantidade de palavras digitadas no prompt (incluindo o nome do próprio programa).

- ***argv (Argument Vector):*** Um array de strings que guarda as palavras digitadas.

**Em casos de bibliotecas adicionais:**
```c
clang -o hello hello.c -lcs50 //-l de library
./hello
```
--------
### #Include
```c
#include <cs50.h>
=
string get_string (string prompt);
```
- Ou seja, #include na verdade é um comando que substitui a menção do "protótipo" de uma determinada função, como forma de "ensinar" o compilador sobre a sua definição e sua funcionalidade dentro do código.
-------
### Termologia e Processo de Compilação:

1. **Preprocessing:** Converte #include em qualquer que seja o protótipo abaixo + outras funcionalidades
2.  **Compiling:** "Catch-all phrase" que converte o código para Assembly
3.  **Assembling:** Pega o codigo em assembly e converte para código binário
4.  **Linking:** Linka os arquivos compilados criados durante todo esse processo com o código binario, finalizando com um único arquivo ("hello" nesse caso)
    -  ```c
        hello.c
        cs50.c
        stdio.c
        ```
------
### (Continuar Estudos: 26:22)