# Atividade 2 - Técnicas clássicas de encriptação - Respostas

## 1. Responda (de forma objetiva) as questões a seguir:

### a) Quais são os elementos essenciais de uma cifra simétrica?

### b) Quais são as duas funções básicas usadas nos algoritmos de encriptação?

### c) Qual é a diferença entre uma cifra de bloco e uma cifra de fluxo?

### d) Quais são as duas técnicas gerais para atacar uma cifra?

### e) Quais são os dois problemas com o one-time pad?

### f) O que é uma cifra de transposição?

### g) O que é esteganografia?

#### a) Resposta:
Os elementos essenciais de uma cifra simétrica são: uma chave e um algoritmo de cifragem/decifragem. A mesma chave é usada tanto para cifrar quanto para descifrar a mensagem.

#### b) Resposta:
As duas funções básicas usadas nos algoritmos de encriptação são: a função de cifragem (que transforma o texto claro em texto cifrado) e a função de decifragem (que transforma o texto cifrado de volta para o texto claro)

#### c) Resposta:
A diferença entre uma cifra de bloco e uma cifra de fluxo é a forma como elas operam. Uma cifra de bloco cifra os dados em blocos fixos de tamanho, enquanto uma cifra de fluxo cifra os dados bit a bit ou byte a byte, normalmente em tempo real.

#### d) Resposta:
As duas técnicas gerais para atacar uma cifra são: ataque de força bruta (tentativa sistemática de todas as chaves possíveis) e criptoanálise (exploração de fraquezas no algoritmo para encontrar a chave ou a mensagem sem a chave).

#### e) Resposta:
Os dois problemas com o one-time pad são a necessidade de chaves extremamente longas e aleatórias, o que pode ser impraticável em muitas situações, e a dificuldade de distribuir chaves únicas e seguras para ambas as partes.

#### f) Resposta:
Uma cifra de transposição é um tipo de cifra na qual as posições dos caracteres no texto são alteradas de acordo com um determinado sistema. Em vez de substituir os caracteres, como nas cifras de substituição, os caracteres são rearranjados.

#### g) Resposta:
Esteganografia é a prática de ocultar informações dentro de outros dados (como imagens, áudio, texto, etc.) de forma que a presença da informação oculta seja imperceptível para observadores não autorizados.

## 2. Uma generalização da cifra de César, conhecida como cifra de César afim, tem a seguinte forma:a cada letra de texto claro p, substitua-a pela letra de texto cifrado C : $$ C = E([a, b], p) = (ap + b) mod 26 $$ um requisito básico de qualquer algoritmo de encriptação é que ele seja um para um. Ou seja, se $p \neq q$, então $E(k, p) \neq E(k, q)$. Caso contrário, a decriptação é impossível, pois mais de um caractere de texto claro é mapeado no mesmo caractere de texto cifrado. A cifra de César afim não é um-para-um para todos os valores de a. Por exemplo, para $a = 2$ e $b = 3$, então $E([a, b], 0) = E([a, b], 13) = 3$.

### a) existem limitações sobre o valor de b? explique por que sim ou por que não.

### b) determine quais valores de a não são permitidos.

### c) ofereça uma afirmação geral sobre quais valores de a são e não são permitidos. Justifique-a.

#### a) Resposta:

O valor de 'b' na cifra não tem limitações específicas para alcançar unicidade, pois é um deslocamento sem impacto na reversibilidade. 

### b) Resposta:

Para garantir a unicidade da cifra (um-para-um), é fundamental que a função de criptografia seja reversível. Para isso, 'a' e 26 precisam ser primos entre si, evitando a perda de injetividade e tornando a decodificação possível.

### c) Resposta:

Como visto anteriormente, 'a' tem que ser um número ímpar, pois garante que ele é coprimo com 26.

## 3.
### a) Encripte a mensagem “meet me at the usual place at ten rather than eight oclock” usando a cifra de Hill com a chave $ \begin{bmatrix} 9 & 4 \\ 5 & 7 \end{bmatrix}$. Mostre seus cálculos e o resultado.

### b) Mostre os cálculos para a decriptação correspondente do texto cifrado a fim de recuperar o texto claro original.

#### a) Resposta:

Iremos realizar a cifragem do texto claro considerando blocos que contém um par de caracteres.
Lembrando que cada caractere representa um número, por exemplo o A representa o  1, o B representa o 2 e assim sucessivamente.
Então o calculo realizado será o seguinte:

[[Chave]] * [[Letras(em naturais)]] % 26 = [[Texto cifrado]]

Acima seria a representação do calculo realizado para obter o texto cifrado, onde há a multiplicação entre a matriz que contém a chave e a matriz que contém o par de caracteres a ser cifrado. Após isso é tirado o mod 26 da matriz resultante. Com isso obtemos o texto cifrado.

Realizando esses calculos obtive o seguinte texto cifrado:

```text
GVUIGVKODZYPUHEKJHUZWFZFWSJSDZMUDZMYCJQMFWWUQRMB
```




#### b) Resposta:

Para descriptografar, é essencial possuir o inverso multiplicativo modular do determinante da chave, obtido a partir do determinante da própria chave, e também a matriz inversa correspondente à chave. A partir do momento que tenho calculado essas informações, conseguimos obter a chave decodificadora. Possuindo a chave decodificadora, basta realizar o mesmo processo que ocorreu na letra anterior:

[[Chave decodificadora]] * [[Texto cifrado(em naturais)]] % 26 = [[Texto claro]]



## 4. Elabore um programa que possa encriptar e decriptar usando a cifra de César geral, também conhecida como cifra aditiva.

#### Resposta:

```python

def cifra_cesar(texto, chave, modo):
    resultado = ''

    for caractere in texto:
        if caractere.isalpha():
            # Verifica se o caractere é uma letra
            maiuscula = caractere.isupper()
            caractere = caractere.lower()

            # Aplica a cifra de César
            if modo == 'encriptar':
                novo_codigo = (ord(caractere) + chave - ord('a')) % 26 + ord('a')
            elif modo == 'decriptar':
                novo_codigo = (ord(caractere) - chave - ord('a')) % 26 + ord('a')

            novo_caractere = chr(novo_codigo)

            # Converte de volta para maiúscula, se necessário
            if maiuscula:
                novo_caractere = novo_caractere.upper()

            resultado += novo_caractere
        else:
            # Mantém caracteres não alfabéticos inalterados
            resultado += caractere

    return resultado

# Exemplo de uso:
texto_original = "Texto claro"
chave = 3
texto_encriptado = cifra_cesar(texto_original, chave, 'encriptar')
texto_decriptado = cifra_cesar(texto_encriptado, chave, 'decriptar')

print("Texto original:", texto_original)
print("Texto encriptado:", texto_encriptado)
print("Texto decriptado:", texto_decriptado)


```

## 5. Elabore um programa que possa realizar um ataque de frequência de letra em uma cifra aditiva sem intervenção humana. Seu software deverá produzir textos claros possíveis em ordem aproximada de probabilidade. Seria bom se a sua interface com o usuário permitisse que ele especificasse “mostre os 10 textos claros mais prováveis”.

#### Resposta:

## 6. Crie um software que possa encriptar e decriptar usando uma cifra de Hill 2 × 2.

```python
import numpy


#Esta função cria uma matriz 3x3
#a partir da chave fornecida, onde os elementos da matriz
#são os valores numéricos equivalentes às letras da chave.
def create_matrix_from(key):
    m=[[0] * 3 for i in range(3)]
    for i in range(3):
        for j in range(3):
            m[i][j] = ord(key[3*i+j]) % 65
    return m




# C = P*K mod 26
def encrypt(P, K):
    C=[0,0,0]
    C[0] = (K[0][0]*P[0] + K[1][0]*P[1] + K[2][0]*P[2]) % 26
    C[1] = (K[0][1]*P[0] + K[1][1]*P[1] + K[2][1]*P[2]) % 26
    C[2] = (K[0][2]*P[0] + K[1][2]*P[1] + K[2][2]*P[2]) % 26
    return C


#Esta função divide a mensagem em blocos de três letras e, em seguida, criptografa cada bloco
def Hill(message, K):
    cipher_text = []
    #Transformando a mensagem em 3 caracteres por vez
    for i in range(0,len(message), 3):
        P=[0, 0, 0]
        #Atribua o valor inteiro correspondente a cada letra
        for j in range(3):
            P[j] = ord(message[i+j]) % 65
        #Criptografar três letras
        C = encrypt(P,K)
        #Adicione as 3 letras criptografadas ao texto cifrado final
        for j in range(3):
            cipher_text.append(chr(C[j] + 65))
        #Repita até que todos os conjuntos de três letras sejam processados.


    #retornar uma string
    return "".join(cipher_text)


#Esta função calcula a matriz inversa de K em módulo 26 usando a inversa multiplicativa modular.
def MatrixInverse(K):
    det = int(numpy.linalg.det(K))
    det_multiplicative_inverse = pow(det, -1, 26)
    K_inv = [[0] * 3 for i in range(3)]
    for i in range(3):
        for j in range(3):
            Dji = K
            Dji = numpy.delete(Dji, (j), axis=0)
            Dji = numpy.delete(Dji, (i), axis=1)
            det = Dji[0][0]*Dji[1][1] - Dji[0][1]*Dji[1][0]
            K_inv[i][j] = (det_multiplicative_inverse * pow(-1,i+j) * det) % 26
    return K_inv




if __name__ == "__main__":


    message = "MYSECRETMESSAGE"
    key = "RRFVSVCCT"
    #Crie a matriz K que será usada como chave
    K = create_matrix_from(key)
    print(K)
    # C = P * K mod 26
    cipher_text = Hill(message, K)
    print ('Cipher text: ', cipher_text)




    # Decrypt
    # P = C * K^-1 mod 26
    K_inv = MatrixInverse(K)
    plain_text = Hill(cipher_text, K_inv)
    print ('Plain text: ', plain_text)


# K x K^-1 verificando se a matriz é igual à matriz identidade
    M = (numpy.dot(K,K_inv))
    for i in range(3):
        for j in range(3):
            M[i][j] = M[i][j] % 26
    print(M)
```