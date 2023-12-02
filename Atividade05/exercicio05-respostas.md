# Atividade 5 - AES - Respostas

## 1° Qual foi o conjunto original de critérios usados pelo NIST para avaliar as cifras AES candidatas?

#### Resposta: 
O conjunto original de critérios(1997) considerados pela NIST inicialmente foram:
- 1. Segurança: ela foi o fator mais importante na avaliação e abrangeu características como resistência do algoritmo à criptoanálise, solidez de sua base matemática, aleatoriedade da saída do algoritmo e segurança relativa em comparação com outros candidatos.
- 2. Custo: O custo foi uma segunda área importante de avaliação que abrangeu requisitos de licenciamento, eficiência computacional (velocidade) em diversas plataformas e requisitos de memória.
- 3. Características de algoritmo e implementação: A terceira área de avaliação foram características de algoritmo e implementação, como flexibilidade, adequação de hardware e software e simplicidade de algoritmo.

## 2° Qual foi o conjunto final de critérios usados pelo NIST para avaliar as cifras AES candidatas?

#### Resposta:
O conjunto final de critérios(2000) considerados pela NIST inicialmente foram:
- 1. Segurança geral: Para avaliar a segurança geral, o NIST baseou-se na análise de segurança pública conduzida pela comunidade criptográfica. Durante o processo de avaliação de três anos, vários criptógrafos publicaram suas análises dos pontos fortes e fracos dos vários candidatos.
- 2. Implementações de software: As principais preocupações nesta categoria são a velocidade de execução, o desempenho em diversas plataformas e a variação de velocidade com o tamanho da chave.
- 3. Ambientes de espaço restrito: Em algumas aplicações, como cartões inteligentes, quantidades relativamente pequenas de memória de acesso aleatório (RAM) e/ou memória somente leitura (ROM) estão disponíveis para fins como armazenamento de código (geralmente em ROM).
- 4. Implementações de hardware: assim como o software, as implementações de hardware podem ser otimizadas em termos de velocidade ou tamanho. 
- 5. Ataques a implementações: O critério de segurança geral, discutido no primeiro item, preocupa-se com ataques criptoanalíticos que exploram propriedades matemáticas dos algoritmos. Existe outra classe de ataques que utiliza medições físicas realizadas durante a execução do algoritmo para coletar informações sobre quantidades, como chaves.
- 6. Criptografia versus descriptografia: Este critério trata de diversas questões relacionadas a considerações de criptografia e descriptografia

## 3° Qual foi o conjunto final de critérios usados pelo NIST para avaliar as cifras AES candidatas?

#### Resposta:

Rijndael é um algoritmo mais genérico que oferece suporte a vários tamanhos de chave e bloco. Já o AES é uma implementação específica do Rijndael, com parâmetros fixos definidos pelo NIST para estabelecer um padrão de cifra simétrica.

## 4. Responda:
### (a) Qual é a finalidade do array Estado?
### (b) Como é construída a S-box?
### (c) Descreva rapidamente o estágio SubBytes, ShiftRows, MixColumns, AddRoundKey, e o algoritmo de expansão de chave.

#### a) Resposta:

O array estado é responsável por salvar as operações realizadas sobre o texto claro durante as fases de encriptação ou decriptação. Após a etapa final, o array estado é copiado para uma matriz de saida.

#### b) Resposta:

A S-box (Substitution box) é uma tabela de substituição usada no AES. Ela substitui cada byte do array Estado por outro byte de acordo com uma tabela predefinida. A construção da S-box envolve uma série de operações, incluindo a aplicação de uma função de inversão, operações de campo finito e permutações. A S-box é projetada para fornecer não linearidade e confusão, contribuindo para a segurança global do algoritmo AES.

#### c) Resposta:

- SubBytes: utiliza uma matriz S-box para realizar uma substituição byte a byte do bloco. Onde, por exemplo, para um hexadecimal A5 iriamos encontrar o elemento que está na linha A e coluna 5 na matriz S-box.

- ShiftRows: realiza uma permutação simples e circular entre os elementos do array de estados para esquerda na encriptação e para direita na decriptação. Sendo que a linha 0 não ocorre mudanças, na linha 1 ocorre o deslocamento de 1 byte, na linha 2 ocorre o deslocamenta de 2 byte, na linha 3 ocorre o deslocamento de 3 byte.

- MixColumns:  cada byte de uma coluna é mapeado para um novo valor que é determinado em função de todos os quatro bytes nessa coluna. A transformação pode ser definida por uma multiplicação de matriz sobre o array de estado. Então, trata-se de uma substituição que utiliza aritmética sobre GF(2<sup>8</sup>).
 

- AddRoundKey: os 128 bits de Estado passam por um XOR bit a bit com os 128 bits da chave da rodada. A operação é vista como uma do tipo coluna por coluna entre os 4 bytes da coluna Estado e uma palavra da chave da rodada.

- Algoritmo de expansão de chave: utiliza como entrada uma chave de 4 words (16 bytes) e produz um array linear de 44 words (176 bytes). Isso é suficiente para oferecer uma chave da rodada de 4 words para o estágio AddRoundKey inicial e para cada uma das 10 rodadas da cifra.

## 5. Quantos bytes em Estado são afetados por ShiftRows?

#### Resposta:

Durante o ShiftRows cada linha é deslocada para esquerda resultando nos seguintes números de bytes, considerando o array de estado:

1 - Nenhuma mudança na primeira linha.

2 - Deslocamento de 1 byte na segunda linha.

3 - Deslocamento de 2 bytes na terceira linha.

4 - Deslocamento de 3 bytes na quarta linha.

Somando no total temos = 6 bytes afetados.

## 6. Use a chave 1010 0111 0011 1011 para encriptar o texto claro "ok"conforme expresso em ASCII, ou seja, 0110 1111 0110 1011. Os projetistas do S-AES obtiveram o texto cifrado 0000 0111 0011 1000. E você?

#### Resposta:

Rodada 0 (Round 0):

Após a adição da chave da rodada (Add round key): 1100 1000 0101 0000
Rodada 1 (Round 1):

Após a substituição de nibbles (Substitute nibbles): 1100 0110 0001 1001

Após o deslocamento de linhas (Shift rows): 1100 1001 0001 0110

Após a mistura de colunas (Mix columns): 1110 1100 1010 0010

Após a adição da chave da rodada (Add round key): 1110 1100 1010 0010

Rodada 2 (Round 2):

Após a substituição de nibbles: 1111 0000 1000 0101

Após o deslocamento de linhas: 0111 0001 0110 1001

Após a adição da chave da rodada: 0000 0111 0011 1000

Portanto, o texto cifrado após duas rodadas é 0000 0111 0011 1000, que corresponde ao que os designers do S-AES obtiveram.



#### Resposta:

## 7. Compare AES com DES. Para cada um dos seguintes elementos do DES, indique o elemento comparável no AES ou explique por que ele não é necessário no AES.
(a) XOR do material da subchave com a entrada da função f.

(b) XOR da saída da função f com a metade esquerda do bloco.

(c) função f.

(d) permutação P.

(e) troca de metades do bloco.

#### a) Resposta: 

No DES, executamos XOR na subchave com a entrada da função ao longo de cada uma das 16 rodadas. Com o AES, seguimos o mesmo procedimento, realizando uma operação XOR entre a subchave e a entrada em cada uma das 10 rodadas antes de passar para a próxima.

#### b) Resposta: 

No DES, a permutação de expansão de 32 bits para 48 bits é seguida por uma operação XOR no lado esquerdo do bloco. Porém, como AES não é criptografia baseado na cifra de Feistel, a operação XOR não é realizada para o meio bloco esquerdo no AES. Com o AES, cada bit é tratado como um bloco separado.

#### c) Resposta: 

A função f corresponde à expansão, mistura, substituição e permutação do DES. AES não é uma cifra fixa, portanto a função é diferente.

#### d) Resposta:

Enquanto o DES usa permutações inicial e final como parte integrante do processo, o AES emprega outras operações que não incluem uma permutação P específica, mas tem o shiftrows que trata de permutação entre bytes.

#### e) Resposta:

No DES, os blocos esquerdo e direito são trocados após cada rodada. O AES evita essa troca tratando todo o bloco de texto simples como uma única unidade e executando operações em todo o bloco de uma só vez.

## 8. Calcule a saída da transformação MixColumns para a seguinte sequência de bytes de entrada "67 89 AB CD". Aplique a transformação InvMixColumns ao resultado obtido para verificar seus cálculos. Altere o primeiro byte da entrada de "67"para "77", realize a transformação MixColumns novamente para a nova entrada e determine quantos bits mudaram na saída.

#### Resposta:

Na operação mixcolumns, cada byte de uma coluna é gerado como um novo valor adicionando todos os quatro bytes dessa coluna, portanto para operação de colunas mistas teremos:
![Alt text](/Atividade05/Imagens/p1-atv05.png)

Aplicando a transformação InvMixColumns ao resultado obtido:
![Alt text](/Atividade05/Imagens/p2-atv05.png)

Agora mudando o primeiro bit na entrada, teremos:
![Alt text](/Atividade05/Imagens/p3-atv05.png)

O número de bits alterados na saída é 5.
