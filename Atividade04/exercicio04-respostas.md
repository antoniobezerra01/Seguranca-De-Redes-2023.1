# Atividade 4 - Conceitos básicos de Teoria dos Números e Corpos Finitos  - Respostas

## 1. Defina resumidamente, um grupo, um anel, um corpo.

### Resposta:

Um grupo G é um conjunto de elementos com uma operação binaria, sinalizada por ., que associa a cada par ordenado (a, b) de elementos em G um elemento (a  b) em G, tal que os axiomas (A1) Fechamento, (A2) Associativo, (A3) Elemento identidade, (A4)  Elemento inverso e (A5) Comutativo.
Um anel R, às vezes indicado por {R, +, ×}, é um conjunto de elementos com duas operações binárias, chamadas adição e multiplicação. Assim como os grupos, deve obedecer esses axiomas:(A1-A5). Além desse tem esses outros: (M1) Fechamento sob multiplicação, (M2) Associatividade da multiplicação, (M3) Leis distributivas, (M4) Comutatividade da multiplicação, (M5) Identidade multiplicativa e (M6) Sem divisores de zero.
Um corpo C é um conjunto de elementos com duas operações binárias, chamadas de adição e multiplicação. Assim como os grupos, deve obedecer esses axiomas:(A1-A5) e (M1-M6). Além desse tem esse outro: (M7)Inverso multiplicativo.

## 2. O que significa dizer que b é um divisor de a?

### Resposta:

Dizer que b é um divisor de a significa que a pode ser dividido por b sem deixar um resto. Em outras palavras, existe um número inteiro q tal que a=b×q.

## 3. Para cada uma das seguintes equações, encontre um inteiro x que satisfaça:

### a) 5x ≡ 4 (mod 3)
### b) 7x ≡ 6 (mod 5)
### c) 9x ≡ 8 (mod 7)

#### a) Resposta:
#### b) Resposta:
#### c) Resposta:
#### d) Resposta:

## 4. Encontre o inverso multiplicativo de cada elemento diferente de zero em $Z_5$.

#### Resposta:

a ⋅ b ≡ 1 (mod n)

a=1

1 ⋅ 1 = 1 (mod 5)
Inverso multiplicativo de 1 é 1.

a=2

2 ⋅ 3 = 1 (mod 5)
Inverso multiplicativo de 2 é 3.

a=3

3 ⋅ 2 = 1 (mod 5)
Inverso multiplicativo de 3 é 2.

a=4

4 ⋅ 4 = 1 (mod 5)
Inverso multiplicativo de 4 é 4.


## 5. Determine os MDC:

### a) mdc(24140, 16762)
### b) mdc(4655, 12075)

#### a) Resposta:
 O mdc entre eles é:34
#### b) Resposta:
 O mdc entre eles é:35
## 6. Usando o algoritmo de Euclides estendido, encontre o inverso multiplicativo de:

### a) 1234 mod 4321;
### b) 24140 mod 40902;
### c) 550 mod 1769.

#### a) Resposta:
O inverso multiplicativo de 1234 modulo 4321 é 3239
#### b) Resposta:
24140 não é coprimo com 40902
#### c) Resposta:
O inverso multiplicativo de 550 modulo 1769 é 550

## 7. Determine o inverso multiplicativo de x^3 + x + 1 em $GF(2^4)$, com $m(x) = x^4 + x + 1$

## 8. Para a aritmética de polinômios com coeficientes em $Z^{10}$, realize os seguintes cálculos:

### a) $(7x + 2) − (x^2 + 5)$
### b) $((6x^2 + x + 3) × (5x^2 + 2))$

#### a) Resposta:

$$ 7x + 2- x^2-5 \Rightarrow -x2+7x-3 \; em \; Z_{10}
 $$

#### b) Resposta:

$$ 30x^4+12x^3+18x^2+5x^3+2x+3 \Rightarrow 30x^4+17x^3+18x^2+2x+3 $$

Após isso, devemos realizar o mod 10 nos coeficientes, com isso teremos o seguinte:

$$ \Rightarrow 7x^3+8x^2+2x+3 \; em \; Z_{10} $$

## 9. Estruture uma calculadora simples de quatro funções em $GF(2^4)$. Você pode usar uma tabela com valores pré-calculados para os inversos multiplicativos.