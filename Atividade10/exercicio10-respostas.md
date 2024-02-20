# Atividade 10 - Outros criptossistemas de chave pública  - Respostas

## 1. Os usuários A e B utilizam a técnica de troca de chaves Diffie-Hellman com um primo comum q = 71 e uma raiz primitiva α = 7.

### a) Se o usuário A tem chave privada $X_A = 5$, qual é a chave pública de A, $Y_A$?
### b) Se o usuário B tem chave privada $X_B$ = 12, qual é a chave pública de B, $Y_B$?
### c) Qual é a chave secreta compartilhada?

#### a) Resposta:

Para calcular a chave pública, elevamos a raiz primitiva à chave privada, calculando o módulo do número primo, ou seja, $α^X$ mod q.

Portanto, para encontrar $Y_A$, fazemos $7^5$ mod 71, que resulta em 16807 mod 71, que é igual a 51.

#### b) Resposta:

Para calcular $Y_B$ aplicamos a operação 712 mod 71, o que nos dá 13841287201 mod 71, resultando em 4.

#### c) Resposta:

Para chegar no segredo, devemos considerar o calculo da chave pública de um elevado a chave privada do outro módulo primo.

$(Y_B)^{X_A} \, mod \,q \Rigtharrow (4)^{5} \, mod \,71 = 30$
$(Y_A)^{X_B} \, mod \,q \Rigtharrow (51)^{12} \, mod \,71 = 30$

## 2. Considere um esquema Elgamal com um primo comum q = 71 e uma raiz primitiva α = 7.

### Resposta:

### a) Se B tem chave pública YB = 3 e A escolheu um inteiro aleatório k = 2, qual é o texto cifrado de M = 30?

### b) Se A, então, selecionar um valor diferente de k, de modo que a codificação de M = 30 seja C = (59, $C_2$), qual é o inteiro $C_2$?