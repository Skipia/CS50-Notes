# Anotações sobre "C"
## Aula CS50 - 2024 Version


- Um Compilador traduz um Código-Fonte para Código de Máquina (Source Code to Machine Code)

>O "Símbolo" para indicar um arquivo C é  " .c "  
>Ex: hello.c
---------
### Comandos Básicos:

- Criar Arquivo:
```c
code hello.c
```

- Compilar Arquivo:
```c
make hello
```
- Rodar o Código:
```c
./hello
```
---------

### Analisando Códigos:   
      
#### Hello World:
````c
#include <stdio.h>

int main(void)
{
    printf("hello, world\n");
}
````
- _**#include:**_ É uma diretiva de pré-processamento (comando que inclui bibliotecas)
- _**int:**_ Retorno esperado como número inteiro
- _**main():**_ Função que indica por onde a execução do código deve começar
- _**void:**_ Parâmetro vazio (não precisa de argumentos extras para ser executado)
- _**\n:**_ Comando que move o cursor para a proxima linha do código
- _**printf():**_ Comando para Escrever Mensagem

---  

#### What's your name?:
````c
#include <stdio.h>

int main(void)
{
    string answer = get_string ("What's your name? ");
    printf("hello, %s\n", answer);
}
````
- _**string:**_ Tipo de dado a ser armazenado
  - No C puro, string não existe! O C usa char *. O pessoal de Harvard criou o tipo string na biblioteca <cs50.h> apenas para facilitar.
- _**answer:**_ Nome da variável (poderia ser outra coisa)
- _**get_string():**_ Chamada da Função (resposta do usuário / valor que ele vai atribuir)
  - _**" = "**_  Significa Atribuição
- _**%s:**_ placeholder (marcador de posição) ou especificador de formato.

-------
### Tipos de Dados 
- bool
- char (Apenas um caractere)
- double
- float
- int
- long
- string (um ou mais caracteres)
- ...

#### Format Codes:
-  _**%c:**_ (Caracteres Simples)
-  _**%f:**_ float (Ponto flutuante decimal)
-  _**%i:**_ inteiros decimais com sinal + (numeros inteiros)
-  _**%li / %LF:**_ Long Double (Números inteiros longos)
-  _**%s:**_ (Cadeia de Caracteres)
-  _**%d:**_ (Int - numero decimal com sinal)
---------
### Comandos para definir o tipo de resposta esperada:

- _**Get_char:**_ Apenas um único caractere (lista, símbolo, espaço)
- _**Get_double:**_ Números Decimais (Precisão Dupla - Dobro de bits do float)
- _**Get_float:**_ Números Decimais (Precisão Simples)
- _**Get_int:**_ Números Inteiros (32 bits)
- _**Get_long:**_ Números Inteiros (64 bits)
- _**Get_string:**_ Sequência de Caracteres (palavras ou frases)
- ------
### Condicionais:
````c
if (x < y) 
{
    printf("x is less than y\n");
}
else if (x > y)
{
    printf("x is greater than y\n");
}
else 
{
    printf("x is equal than y\n");
}
````
-------
#### Termo de Permissão
````c
#include <stdio.h>
#include <cs50.h>

int main(void)
{
    char c = get_char("Do you agree? ");

    if (c == 'y' || c == 'Y') // "||" significa "ou"
    {
        printf("Agreed.\n");
    }
    else if (c == 'n' || c == 'N')
    {
        printf("Not agreed.\n");
    }
    else
    {
        printf("Invalid input.\n");
    }
}
````
------------
### Variaveis
#### Contador:
Sintaxe Comum:
```c
int counter = 0;
```
Formas de Adicionar um valor ao Contador:
```c
counter = counter + 1;
counter += 1;
counter ++;
// Ambos os três são iguais
```

Formas de Subtrair um valor ao Contador:
```c
counter = counter - 1;
counter -= 1;
counter --;
// Ambos os três são iguais
```
--------
### Loops
#### While
```c
int counter = 3;
while (counter > 0)
{
    printf("meow\n");
    counter = counter - 1;
}
```
=
```c
int i = 3;
while (i > 0)
{
    printf("meow\n");
    i--;
}
```

#### Do
```c
int main(void)
{
    int n; //Declarei fora para evitar bug no resto do código.
    do
    {
         n = get_int("Size: ");
    }
    while (n < 1);

    //Print an n-by-n grid of bricks
    for(int i = 0; i < n; i++)
    {
        for(int j = 0; j < n; j++)
        {
            printf("#");
        }
        printf("\n");
    }
}
```
---------
### Funções:
```c
void meow(void) //Função "Meow"
{
    printf("meow\n");
}


int main(void)
{
    for (int i = 0; i < 3; i++)
    {
        meow();
    }
}
```
**OBS:** Para evitar de afastar muito a função "main" da função criada, cite a linha da função no inicio do código também;
```c
void meow(void)

int main(void)
{
    for (int i = 0; i < 3; i++)
    {
        meow();
    }
}


void meow(void) //Função "Meow"
{
    printf("meow\n");
}
//O ideal é que a função criada fique sempre no topo pra não bugar o código
```
-----------
### Operadores Lógicos
- _**" + ":**_ Adição
- _**" - ":**_ Subtração
- _**" / ":**_ Divisão
- _**" * ":**_ Multiplicação
- _**" % ":**_ "Resto" da divisão (Operador de Módulo)

-----------
### Escopo:
- É o contexto em que cada variável existe (dentro de uma determinada função ou fora dela, por exemplo.)

```c
int add(int a, int b); //Sempre colocar a referencia da função (protótipo) antes do código em si pra não bugar.

int main(void)
{
    int x = get_int("x: ");
    int y = get_int("y: ");

    int z = add(x, y); //A variável z é dispensavel pela lógica matemática
    printf("%i\n" , z); 
}


int add(int a, int b) //Dois parâmetros de números inteiros a serem retornados pelo usuário (input)
{
    return a + b;
}
```

- O conceito de funções em computação é relativamente analoga à concepção matemática (incluindo conceitos de função composta).
-----------
### **Curiosidade:** 
- Sempre que você escreve um programa e roda ele, o mesmo acaba retornando um "valor invisível"(0 por convenção, o que indica que o pragrama está rodando devidamente).
- Quando há algum problema em alguma das funções, outro valor é retornado (o número indica onde foi o erro). Exemplo: Erros de aplicativo de celular/pc como "Erro 204". 
--------
### LINUX:
- Muito utilizado por entusiástas e servidores; Envolve muita programação e conhecimentos "autodidatas"
- GUI: Graphical User Interface
- CLI: Command Line Interface
- O CS50 utilizou o sistema LINUX para facilitar a interação dos estudantes com as interfaces, sincronizando em nuvens e armazenando dados em diferentes servidores.

#### Comandos Textuais mais Populares:

- _**" cd ":**_ (Change Directory): Serve para entrar ou sair de pastas.
  - "cd Documentos": entra na pasta.
  - "cd .." (dois pontos): volta para a pasta anterior.
- _**" cp ":**_ (Copy): Copia um arquivo de um lugar para outro.
- _**" ls ":**_ (List): Mostra o que tem dentro da pasta onde você está
- _**" mkdir ":**_ (Make Directory): Cria uma pasta nova. Ex: mkdir exercicios_c.
- _**" mv ":**_ (Move): Move um arquivo (ou renomeia ele!). Se você mover teste.c para final.c, você o renomeou.
- _**" rm ":**_ (Remove): Apaga um arquivo. Atenção: No terminal não tem "Lixeira". Apagou, sumiu.
- _**" rmdir ":**_ (Remove Directory): Apaga uma pasta, mas ela precisa estar vazia. Para apagar uma pasta com coisas dentro, o pessoal de BCC costuma usar rm -rf (use com extrema cautela!).
- ...

#### Truques e Comandos para a Interface do Terminal Linux (VS Code):
- "Seta para Cima": Altera entre "make" e "./" comando
- "Tab": Complementa o que você estava escrevendo (Probabilidade)
---------
### Constantes
- Quando é necessário uma variável "fixa" (para não altera-la acidentalmente)
```c
int main(void)
{
    const int n = 5;
    for (int i = 0; i < n; i++)
    {
        for (int j = 0; j < n; j++) //Notavelmente há repetições desnecessárias;
        {
            printf("#");
        }
        printf("\n");
    }
}
```
----------
### Integer Overflow:
- Integer Overflow ocorre quando uma operação aritmética excede a capacidade do tipo de dado. Por exemplo, em um sistema de 8 bits (máximo 255), somar 1 a 255 faz o valor retornar a 0 ou a um número negativo  (wraparound). 
- Isso pode causar erros de lógica graves ou vulnerabilidades de segurança, como buffer overflows. Para evitar, deve-se validar entradas, usar tipos de dados maiores ou funções que detectam overflow automaticamente.
------
### Trucation (Truncamento):
- Ocorre quando um dado é "cortado" para caber em um espaço de armazenamento menor do que o necessário. Diferente do overflow, onde o valor "dá a volta", no truncamento os bits ou caracteres excedentes são simplesmente descartados.

#### Type Casting
- Converção de tipos de variáveis durante o código.

```c
int main(void)
{
    int x = get_int("x: ");
    int y = get_int("y: ");

    float z = (float) x / (float) y; //casting x and y to floats, so that the division will be done in floating point, and not in integer division
    printf("%f\n", z);
}
```
---------
### Floating-Point Imprecision (Imprecisão de Ponto Flutuante)
- A maioria das linguagens de programação segue o padrão IEEE 754, que armazena números em formato binário científico:
  ```c
  $$\text{Valor} = (-1)^s \times M \times 2^E$$
  ```
  Onde:
  - $s$: Sinal (0 para positivo, 1 para negativo).
  - $M$: Mantissa (fração).
  - $E$: Expoente. 
  
#### 1. O Problema da Base Binária
- Assim como não conseguimos representar $1/3$ de forma exata na base 10 ($0.3333...$), o computador não consegue representar frações como $1/10$ ($0.1$) de forma exata na base 2.
- Representação de 0.1 em binário: 0.0001100110011... (dízima infinita).
- Resultado: O computador corta a dízima, causando um erro minúsculo de arredondamento.

#### 2. Erros Acumulativos
- Embora o erro individual seja minúsculo, ele se torna perigoso em:
  - Comparações Diretas: if (0.1 + 0.2 == 0.3) retornará falso na maioria das linguagens.
  - Loops Longos: Somar valores pequenos repetidamente em um contador pode desviar o resultado final significativamente.
  
#### 3. Perda de Significância (Catastrophic Cancellation)
- Ocorre quando subtraímos dois números muito próximos ou somamos um número gigante com um muito pequeno. O número menor pode ser "engolido" porque não há bits suficientes na mantissa para manter a precisão de ambos.
- Exemplo: 
````c
$10^{16} + 1$ pode resultar apenas em $10^{16}$
````
#### Como Lidar com Isso?
- Nunca use float ou double para dinheiro: Use tipos de precisão decimal fixa (ex: BigDecimal em Java, Decimal em Python) ou armazene apenas centavos como inteiros.
- Comparações com "Epsilon" ($\epsilon$): Em vez de a == b, verifique se a diferença é menor que um limite tolerável:
    - ````c
       if (abs(a - b) < 0.00001)
      ````
- Bibliotecas de Precisão Arbitrária: Para cálculos científicos que exigem exatidão total.
-----------