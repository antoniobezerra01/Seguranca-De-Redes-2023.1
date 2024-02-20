# Atividade 9 - Criptografia de chave pública e RSA  - Respostas

## 1. Quais são os principais elementos de um criptossistema de chave pública?

### Resposta:

- Texto original: A mensagem que você quer proteger.

- Algoritmo de codificação: O processo que vai misturar e transformar o texto original para torná-lo indecifrável.

- Chave de bloqueio e chave de desbloqueio: São como chaves de cadeado, uma para embaralhar (bloquear) a mensagem e outra para desembaralhar (desbloquear) e revelar o conteúdo original.

- Texto codificado: É a mensagem embaralhada após passar pelo algoritmo de codificação. Se alguém tentar lê-la sem a chave correta, não entenderá nada.

- Algoritmo de decodificação: Recebe o texto codificado e a chave correta e reverte o processo de codificação, revelando a mensagem original.

## 2. Quais são os papéis da chave pública e da privada? Descreva-os com detalhes e com exemplos.

### Resposta:

A chave secreta de um usuário é guardada em segredo e somente conhecida por esse usuário. Já a chave pública é compartilhada para que outras pessoas possam utilizá-la.

Essa chave secreta pode ser usada para codificar uma assinatura que qualquer pessoa, tendo a chave pública, pode verificar.

Em outras palavras, a chave pública pode ser usada para codificar dados que só podem ser decodificados pelo dono da chave secreta.

## 3. Quais requisitos os criptossistemas de chave pública precisam cumprir para serem considerados como um algoritmo seguro?

Difícil de Quebrar: O algoritmo deve ser tão robusto que mesmo com muito poder computacional, seria praticamente impossível decifrar a mensagem sem a chave certa.

Complexidade Matemática: Deve ser baseado em problemas matemáticos que são extremamente difíceis de resolver, garantindo que mesmo com muitos recursos, decifrar a mensagem seria uma tarefa formidável.

Invariável com Chave Pública: Mesmo que alguém tenha acesso à chave pública, isso não deve ajudar em nada para descobrir a chave privada ou decifrar a mensagem.

Geração de Chaves Aleatórias: As chaves devem ser geradas de forma completamente aleatória, garantindo que sejam únicas e não previsíveis.

Resistência a Ataques de Chaves Relacionadas: O sistema deve ser resistente mesmo que o invasor tenha acesso a chaves temporárias ou relacionadas.

Proteção contra Ataques de Substituição de Chave: Mesmo que alguém tente substituir uma chave por outra, o sistema deve permanecer seguro.

Resistência a Ataques de Homomorfismo Parcial: O sistema deve ser projetado para resistir a tentativas de deduzir informações sobre a mensagem original através de operações nos textos cifrados.

Padrões Reconhecidos: É importante que o algoritmo seja amplamente revisado pela comunidade de especialistas em segurança e que seja adotado por organizações reconhecidas por sua credibilidade em segurança digital.

## 4. Descreva, em termos gerais, um procedimento eficiente para se escolher um número primo.

### Resposta:

O processo envolve gerar aleatoriamente um número ímpar n e outro número a menor que n. Em seguida, é realizado o teste de primalidade Miller-Rabin em n. Se n falhar no teste, ele é rejeitado e o processo recomeça. Se n passar em um número suficiente de testes, ele é aceito, caso contrário, o processo continua com a geração de um novo número a.

## 6. Realize a encriptação e decriptação usando o algoritmo RSA, como na Figura 9.5, para o seguinte:

### Resposta:

Passo 1: calcular n

Passo 2: calcular ϕ(n)

Passo 3: encontrar d (chave privada) → é o inverso multiplicativo de e módulo ϕ(n)

Passo 4: encriptar

Passo 5: decriptar

(a) p = 3; q = 11, e = 7; M = 5;

n = p*q = 3 * 11 = 33

ϕ(n) = (p-1) * (q-1) = (3-1) * (11-1) = 2 * 10 = 20

d * e ≡ 1 mod ϕ(n) → d * 7 ≡ 1 mod 20 → 3, pois 21/20 deixa resto = 1. Logo, d = 3.

C = Me mod n = 57 mod 33 = 78125 mod 33 = 14

M = Cd mod n = 143 mod 33 = 2744 mod 33 = 5

 

(b) p = 5; q = 11, e = 3; M = 9;

n = p*q = 5 * 11 = 55

ϕ(n) = (p-1) * (q-1) = (5-1) * (11-1) = 4 * 10 = 40

d * e ≡ 1 mod ϕ(n) → d * 3 ≡ 1 mod 40 → 27, pois 81/40 deixa resto = 1. Logo, d = 27.

C = Me mod n = 93 mod 55 = 729 mod 55 = 14

M = Cd mod n = 1427 mod 55 = 9

 

(c) p = 7; q = 11, e = 17; M = 8;

n = p*q = 7 * 11 = 77

ϕ(n) = (p-1) * (q-1) = (7-1) * (11-1) = 6 * 10 = 60

d * e ≡ 1 mod ϕ(n) → d * 17 ≡ 1 mod 60 → 53, pois 901/60 deixa resto = 1. Logo, d = 53.

C = Me mod n = 817 mod 77 = mod 77 = 2251799813685248 mod 77 = 57

M = Cd mod n = 5753 mod 77 = 8

 

(d) p = 11; q = 13, e = 11; M = 7;

n = p*q = 11 * 13 = 143

ϕ(n) = (p-1) * (q-1) = (11-1) * (13-1) = 10 * 12 = 120

d * e ≡ 1 mod ϕ(n) → d * 11 ≡ 1 mod 120 → 11, pois 121/120 deixa resto = 1. Logo, d = 11.

C = Me mod n = 711 mod 143 = 1977326743 mod 143 = 106

M = Cd mod n = 10611 mod 143 = 7

 

(e) p = 17; q = 31, e = 7; M = 2.

n = p*q = 17 * 31 = 527

ϕ(n) = (p-1) * (q-1) = (17-1) * (31-1) = 16 * 30 = 480

d * e ≡ 1 mod ϕ(n) → d * 7 ≡ 1 mod 480 → 343, pois 2401/480 deixa resto = 1. Logo, d = 343.

C = Me mod n = 27 mod 527 = 128 mod 527 = 128

M = Cd mod n = 128343 mod 527 = 2

## 7. Em um sistema de chave pública usando RSA, você intercepta o texto cifrado C = 10 enviado a um usuário cuja chave pública é e = 5, n = 35. Qual é o texto claro M?

### Resposta:

Para decifrar uma mensagem criptografada, usamos a fórmula M = $C^d$ mod n, onde M representa a mensagem original, C é a mensagem cifrada, d é a chave privada e n é o produto dos números primos.

Para o caso específico em que M = 10d mod 35, precisamos encontrar a chave privada d usando a relação e * d mod ϕ(n) = 1.

Para n = 35, com fatores primos 5 e 7, temos ϕ(n) = (5-1) * (7-1) = 4 * 6 = 24.

Buscando d tal que 5 * d mod 24 = 1, encontramos que d é 5.

Agora, aplicando na decriptação, temos: M = $10^5$ mod 35 = 100000 mod 35 = 5.