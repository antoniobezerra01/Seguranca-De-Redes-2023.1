# Atividade 3 - Cifras de bloco e o data encryption standard  - Respostas

## 1. Responda os questionamentos a seguir:

### a) Por que é importante estudar a cifra de Feistel?

### b) Qual é a diferença entre uma cifra de bloco e uma cifra de fluxo?

### c) Por que não é prático usar uma cifra de substituição reversível qualquer do tipo mostrado na Tabela 3.1?

### d) O que é uma cifra de produto?

### e) Qual é a diferença entre difusão e confusão?

### f) Que parâmetros e escolhas de projeto determinam o algoritmo real de uma cifra de Feistel?

### g) Explique o efeito avalanche.

#### a) Resposta:

Estudar a cifra de Feistel é crucial devido à sua ampla aplicação em algoritmos criptográficos modernos, garantindo segurança e eficiência. Essa compreensão é essencial para avaliar a segurança de algoritmos, entender a evolução da criptografia moderna e aprimorar a teoria e prática da segurança da informação.

#### b) Resposta:

Cifra de Bloco: Opera em blocos fixos de dados, cifrando-os independentemente. Exemplo: DES, AES.
Cifra de Fluxo: Ópera em bits ou pequenas unidades, cifrando de forma contínua. Exemplo: RC4.

#### c) Resposta:

Em blocos pequenos, a técnica se assemelha a uma cifra de substituição clássica, vulnerável a análises estatísticas do texto original. Contudo, para blocos extensos, sua aplicação torna-se inviável devido a desafios de implementação e desempenho.

#### d) Resposta:

 É a execução de duas ou mais cifras simples em sequência, de tal forma que o resultado ou produto final seja criptograficamente mais forte do que qualquer uma das cifras componentes. 

#### e) Resposta:

Na difusão, a estrutura estatística do texto claro é dissipada em estatísticas de longa duração do texto cifrado. A confusão procura estabelecer o relacionamento entre as estatísticas do texto cifrado e o valor da chave de encriptação o mais complexo possível, novamente para frustrar tentativas de descobrir a chave.

#### f) Resposta:

O tamanho de bloco, o tamanho da chave e o número de rodadas.

#### g) Resposta:

É uma pequena mudança no texto claro ou na chave que produza uma alteração significativa no texto cifrado.


## 2. Qual(is) dos recursos abaixo estão presentes no projeto da rede de Feistel? Explique.

### (a) Tamanho do bloco e da chave;
### (b) Função da rodada;
### (c) Gerador de sub-chaves;
### (d) Todas as alternativas.

#### Resposta: 
(d) Todas as alternativas. Dado que são componentes utilizados para cifra Feistel.

## 3. Qual é o tamanho do texto claro no Data Encryption Standard (DES)? Explique.

### (a) 57
### (b) 48
### (c) 32
### (d) 64

#### Resposta:

(d) 64. O Data Encryption Standard (DES) opera com blocos de texto claro de 64 bits. Isso significa que cada vez que o algoritmo DES é aplicado, ele cifra ou decifra 64 bits de dados de uma vez. 

## 5. A cifra de Feistel do algoritmo de encriptação utilizada no Data Encryption Standard (DES) utiliza quantos S-boxes? Explique.
### (a) 8;
### (b) 7;
### (c) 6;
### (d) 5.

#### Resposta:

(a) 8. O algoritmo de encriptação utilizado no Data Encryption Standard (DES) utiliza um total de 8 S-boxes em cada rodada do processo de Feistel. Cada S-box é uma tabela de substituição que transforma um conjunto de bits de entrada em um conjunto de bits de saída de acordo com uma regra pré-definida. Eles desempenham um papel crucial na operação do DES e são responsáveis por uma parte significativa da sua segurança

## O Data Encryption Standard possui uma chave de 56 bits, o que torna possível um espaço de $2^{56}$ chaves possíveis. Essa sentença trata de ataque de ... Explique.
### (a) Tempo;
### (b) Matemático;
### (c) Força-Bruta;
### (d) DoS.

#### Resposta:

(c) Força-Bruta. Já que ele considera a execução de todas as combinações possíveis de chaves até verificar a chave correta, a qual é responsável por decifrar o texto cifrado.

## 6. Demonstre, através de um exemplo, como realizar a cifragem de 16 bits (dois caracteres), em 2 rounds, em seguida, decifre o texto cifrado. Explique o processo passo a passo. Forneça um código Python/Sagemath com sua solução.

#### Resposta:

## 7. Considere uma cifra de Feistel composta de 16 rodadas com tamanho de bloco de 128 bits e tamanho de chave de 128 bits. Suponha que, para determinado k, o algoritmo de escalonamento de chave defina valores as oito primeiras chaves de rodada, k1, k2, . . . , k8, e depois estabeleça

#### Resposta:
