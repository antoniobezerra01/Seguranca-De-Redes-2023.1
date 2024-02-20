# Atividade 8 - Mais teoria dos números  - Respostas

## 1. Por que mdc(n, n + 1) = 1 é para dois inteiros consecutivos n e n + 1?

### Resposta:

Se supormos a existência de um primo $p$ que divide tanto $n$ quanto $n+1$, então ele também deveria dividir a diferença entre eles, ou seja, $(n+1) – n$. O resultado dessa diferença sendo 1 implica que $n$ é subtraído de si mesmo.
Porém, nenhum número primo, exceto o 1, pode dividir 1. Isso decorre do fato de que os números primos possuem apenas dois divisores: 1 e o próprio número. Assim, concluímos que o único número primo capaz de dividir $n$, $n+1$ e a diferença entre eles é o 1.

## 2. Usando o teorema de Fermat, encontre $3^{201}$ mod 11.

### Resposta:

Segundo o teorema, quando "p" é um número primo e "a" é um número inteiro positivo que não é divisível por "p", então "a" elevado à potência "p menos um" é congruente a 1, considerando o módulo "p".

$$ a^{p-1} \equiv 1 \, mod \, p $$

Então, 3 elevado a 10 é congruente a 1, considerando o módulo 11. $3^{10} \equiv 1 \, mod \, 11 $.

Assim, 3 elevado a 201 é equivalente a 3 vezes 3 elevado a 200, o que é congruente a 3, considerando o módulo 11. $ 3^{201} = (3^{10})^{20} 	\times 3 \equiv 3 \, mod \, 11 $.

## 3. Use o teorema de Fermat para encontrar um número a entre 0 e 72, com a congruente a 9794 módulo 73.

### Resposta:

Dado que o resto da divisão de 9794 por 73 é 12, o único número neste intervalo que resultará em um resto de 12 quando dividido por 73 é o próprio 12. Portanto, o número procurado é 12, pois 12 é congruente a 9794, considerando o módulo 73.

## 4. Use o teorema de Euler para encontrar um número a entre 0 e 9, tal que a seja congruente a $7^{1000}$ módulo 10. (Observe que isso é o mesmo que o último dígito da expansão decimal de $7^{1000}$.)

### Resposta:

Euler estabelece que $ a^{\phi(n)} \equiv 1 \, mod \, n. $

Como $n=10$, temos que $\phi(n) = 4$, dado que é o tamanho da lista de números relativamente primos menores que 10, que são 1, 3, 7 e 9.

Logo, precisamos encontrar $a^4 \equiv 1 \, mod \, 10$.

Teremos $1^4 \equiv 1\, mod \, 10$, portanto, um número possível é $a=1$.

## 5. Use o teorema de Euler para encontrar um número x entre 0 e 28, com $x^{85}$ congruente a 6 módulo 35 (Você não precisará usar qualquer pesquisa por força bruta).

### Resposta:

Vamos decompor $x^{85}$ em  $x^{24} \times x^{24} \times x^{24} \times x^{13}$. A partir disso, vamos simplificar os três $x^{24}$ para um, pois $x^{\phi(n)} \equiv 1$ e a função totiente de 35 é 24. Seguindo:

$$ a^{24} \equiv 1  \,(mod \, 35) \Rightarrow a^{12} \equiv \pm a = 6\, mod(35) \Rightarrow a = 6 \,ou\, a = -6 $$

Como a solução requer um número entre 0 e 28, temos que a é igual a 6.

## 6. Observe, na Tabela 8.2, que ϕ(n) é par para n > 2. Isso é verdadeiro para todo n > 2. Dê um argumento conciso para explicar por que isso acontece.

### Resposta:

A função ϕ(n) conta quantos números inteiros menores que n não têm nenhum fator em comum com n, exceto o 1.

Se um número a não compartilha nenhum fator comum com n, então n - a também não compartilha. Isso ocorre porque se a não tem nenhum fator comum com n, então n - a não pode ter os mesmos fatores que a.  Em outras palavras, para cada número a que não tem fatores em comum com n, existe um número n - a que também não tem.

## 7. Se n é composto e passa no teste de Miller-Rabin para a base a, então n é chamado de pseudo-primo forte à base a. Mostre que 2047 é um pseudoprimo à base 2.

### Resposta:

Conforme as instruções do livro, o processo é o seguinte:

Primeiramente, no passo 1 da função de teste, atribuímos k = 1 e q = 1023, pois (2047 – 1) = (21) * (1023).

Em seguida, na etapa 2, escolhemos a = 2 como base.

No passo 3, calculamos $a^q \, mod \, n = 2^{1023}\, mod\, 2047 = (2^{11})^{93} \, mod \, 2047 = (2048)^{93}\, mod\, 2047 = 1$. Assim, o teste é considerado bem-sucedido.

## 8. O exemplo usado por Sun-Tsu para ilustrar o CRT foi x ≡ 2 (mod 3); x ≡ 3 (mod 5); x ≡ 2 (mod 7). Solucione para x.
