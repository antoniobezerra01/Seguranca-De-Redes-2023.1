# Atividade 7 - Geração de número pseudoaleatório e cifras de fluxo  - Respostas

## 1. Qual é a diferença entre aleatoriedades estatísticas e imprevisibilidade?

### Resposta:

Aleatoriedades Estatísticas: Refere-se à capacidade de um processo gerar uma sequência de bits que, estatisticamente, se assemelha a uma sequência verdadeiramente aleatória. Mesmo que a sequência não seja verdadeiramente aleatória, ela deve exibir propriedades estatísticas que tornem difícil distinguir entre a sequência gerada e uma sequência aleatória. Isso está relacionado à uniformidade e independência dos bits na sequência.

Imprevisibilidade: Refere-se à dificuldade de prever o próximo bit ou conjunto de bits em uma sequência, mesmo conhecendo parte ou toda a sequência passada. A imprevisibilidade está mais relacionada à resistência a ataques de análise de padrões ou predição.

## 2. Liste considerações de projeto importantes para uma cifra de fluxo.

### Resposta:

Geração de Chave Aleatória: O processo de geração de chave deve ser robusto e garantir uma chave inicial única e aleatória para evitar padrões previsíveis na sequência cifrada.

Não Linearidade: O algoritmo deve incluir operações não lineares para tornar a cifra resistente a ataques diferencias e lineares.

Período Longo: A cifra deve ter um período longo para evitar repetições na sequência cifrada durante um período significativo de tempo.

Distribuição Uniforme: Os bits na sequência cifrada devem ser distribuídos uniformemente para evitar viés estatístico.

Resistência a Ataques Conhecidos-Plaintext: A cifra deve ser resistente a ataques onde um adversário tem conhecimento do texto simples (plaintext) correspondente a uma parte da sequência cifrada.

##  3. Por que não é desejável reutilizar uma chave de cifra de fluxo?

### Resposta:

Vulnerabilidade a Ataques de XOR: Se uma chave de cifra de fluxo é reutilizada, existe o risco de que partes da sequência cifrada resultante também sejam iguais, o que facilita ataques de XOR, onde o atacante pode cancelar bits correspondentes e recuperar informações sobre os textos simples.

Quebra do Segredo da Chave: Reutilizar uma chave de cifra de fluxo pode levar à quebra do segredo da chave, especialmente se parte da sequência cifrada for conhecida. Isso pode comprometer a confidencialidade do sistema.

Perda de Unicidade da Sequência Cifrada: A reutilização de chaves pode levar à repetição de partes da sequência cifrada, o que é indesejável. A unicidade da sequência cifrada é essencial para a segurança da cifra de fluxo.

## 4. Que operações primitivas são usadas no RC4?

### Resposta:

Inicialização do Vetor de Estado:

O algoritmo inicia um vetor de estado (geralmente uma matriz S) com valores sequenciais de 0 a 255.
Permutação do Vetor de Estado (Swap):

O vetor de estado é permutado (reorganizado) com base nas chaves fornecidas. Isso envolve trocar elementos do vetor de estado para criar uma mistura inicial.
Geração de Pseudo-Random Bytes:

A partir do vetor de estado permutado, o algoritmo gera uma sequência pseudo-aleatória de bytes. Esses bytes são usados como chave stream para realizar a operação de XOR com o texto simples, produzindo o texto cifrado.
Operação de XOR (OU Exclusivo):

A operação de OU Exclusivo (XOR) é aplicada entre os bytes do texto simples e os bytes gerados pelo RC4. Isso resulta no texto cifrado.
Essas operações são repetidas para cada byte do texto simples, produzindo a sequência cifrada.

## 5. Se apanharmos um algoritmo de congruência linear com um componente aditivo de 0: $$X_{n+1} = (aX_n) \; mod \; n$$ então, podemos mostrar que, se $m$ é primo, e se determinado valor de $a4 produz o período máximo de $m - 1$, então $a^k$ também produzirá o período máximo, desde que $k$ seja menor que $m$ e que $m-1$ não seja divisível por $k$. Demonstre isso usando $X_0 = 1$ e $m = 31$, e produzindo as sequências para $ak = 3, \;3^2, \;3^3$ e $3^4$.

### Resposta:

## 6.
### a) Qual é o período máximo que pode ser obtido do seguinte gerador? $$ X_{n+1} = (aX_n) \; mod \; 2^4 $$

### b) Qual deverá ser o valor de a?

### c) Que restrições são exigidas na semente?

#### a) Resposta:

O tempo máximo necessário depende de $a$ e de $X_0$. Para $m = 16$, o período máximo ocorre quando $a$ e $X_0$ são escolhidos de forma que $a - 1$ seja divisível por todos os fatores primos de $m$ e $a - 1$ seja múltiplo de 4 se $m$ também o for. Por exemplo, com $a = 5$ e $X0 = 3$, o período máximo é 16, repetindo-se a sequência após 16 termos.

#### b) Resposta:

Para garantir que $a$ atenda aos critérios mencionados na letra anterior, teremos o seguinte:

Para $m = 16$, os fatores primos são 2 e 4, e $m$ é múltiplo de 4.

Uma escolha comum para "a" é 5. Verificando:

- $X_0 = 1$ e $a = 5$ são primos entre si.
- $5 - 1 = 4$ é divisível por 2 e 4.
- $5 - 1 = 4$ é um múltiplo de 4.

Assim, $a = 5$ é uma escolha adequada para alcançar o período máximo no gerador linear congruente especificado.


#### c) Resposta:

- Coprimalidade com $m$: A semente $X_0$ deve ser coprima com o módulo $m$, ou seja, não deve ter fatores primos em comum com $m$, exceto 1. Por exemplo, se $m = 16$, então $X_0$ não deve ser divisível por 2.

- Não pode ser zero: $X_0$ não pode ser zero, a menos que o multiplicador $a$ seja escolhido de uma forma específica. Se $X_0$ for zero e $a$ for um múltiplo de 2, o gerador entrará em um ciclo curto.

- Escolha que não gera um ciclo curto: A semente $X_0$ deve ser escolhida de modo a não gerar um ciclo curto, o que pode ocorrer se $X_0$ for zero ou um múltiplo de $m$.

## 7. Que valor de chave RC4 deixará S inalterado durante a inicialização? Ou seja, após a permutação inicial de S, as entradas de S serão quais aos valores de 0 a 255 na ordem crescente.

### Resposta:

Uma chave composta por 255 bytes, em que os dois primeiros bytes são ambos zero, enquanto os demais seguem uma sequência decrescente, iniciando de 255 até 2. Isso decorre da aplicação do algoritmo da seguinte maneira:

Na primeira iteração, K[0] é definido como 0.
Na segunda iteração, K[1] também é definido como 0.
Na terceira iteração, K[2] é atribuído o valor 255, e esse processo continua até alcançar K[255].
Assim, temos:

K[3]=254;

K[4]=253;

K[5]=252;

Assim segue até:

K[255] = 2.