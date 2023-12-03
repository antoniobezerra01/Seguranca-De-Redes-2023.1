# Atividade 1 - Introdução - Respostas

## 1. O que é a arquitetura de segurança OSI?

#### Resposta:

A segurança de redes pode ser implementada em várias camadas do modelo OSI para proteger a integridade, a confidencialidade e a disponibilidade dos dados em trânsito. Isso pode envolver a criptografia de dados, a autenticação de usuários, o controle de acesso, a detecção de intrusões e outras medidas de segurança. Então, são apresentadas 7 camadas neste modelo, sendo elas: Camada Física, Camada de Enlace de Dados, Camada de Rede, 
Camada de Transporte, Camada de Sessão, Camada de Apresentação e Camada de Aplicação.

## 2. Qual é a diferença entre ameaças à segurança passivas e ativas?

#### Resposta:

As ameaças passivas se concentram principalmente na obtenção de informações sem causar danos diretos, enquanto as ameaças ativas visam prejudicar sistemas ou recursos de alguma forma.

## 3. Liste e defina resumidamente as categorias de ataques passivos e ativos à segurança.

#### Resposta:

- Ataques passivos:

    + Sniffing -  Captura e análise não autorizada de dados em tráfego de rede para obter informações sensíveis.

    + Scanning -  Identificação de portas e serviços disponíveis em um sistema para explorar vulnerabilidades.

    + Interceptação de Dados - Captura de dados em trânsito entre sistemas

- Ataques ativos:

    + Vírus - Programas de software maliciosos que se anexam a outros arquivos e se replicam para danificar ou infectar sistemas

    + DDoS - Sobrecarregamento de um serviço, servidor ou rede para torná-los inacessíveis.

    + Phishing - Tentativa de enganar os usuários para revelar informações confidenciais, geralmente por meio de e-mails falsos.

## 4. Liste e defina resumidamente as categorias dos serviços de segurança.

#### Resposta:

Autenticação: assegura a legitimidade da comunicação, ou seja, certifica ao destinatário que a mensagem realmente provém da fonte que alega.

Controle de acesso: refere-se à restrição do acesso a sistemas, ajustando os privilégios de entrada para entidades previamente identificadas e autenticadas.

Confidencialidade dos dados: implica na salvaguarda das informações transmitidas contra ataques passivos, protegendo o fluxo de tráfego contra análises, conforme explicado anteriormente.

Integridade dos dados: garante que as mensagens sejam recebidas de acordo com o envio, sem ocorrência de duplicação, inserção, modificação, destruição, reordenação ou repasse.

Irretratabilidade: fornece evidências de que as entidades participaram da comunicação, impedindo que neguem a autenticidade de uma mensagem transmitida, ao afirmar que o remetente a enviou e o destinatário a recebeu.

## 5. liste e defina resumidamente as categorias dos mecanismos de segurança.

#### Resposta:

Específicos: são implementados em uma camada de protocolo particular para oferecer serviços de segurança OSI, como codificação, assinatura digital, controle de acesso, integridade de dados e controle de roteamento.

Difusos: não estão restritos a uma camada de protocolo específica ou serviço de segurança, incluindo funcionalidade confiada, detecção de evento, trilha de auditoria de segurança e recuperação de segurança.

Reversíveis: possibilitam a reversão do processo, como um mecanismo de codificação que permite a encriptação seguida de decriptação.

Irreversíveis: não permitem a reversão do processo, exemplificado por algoritmos de hash.

## 6. Considere um caixa eletrônico, ATM no qual os usuários fornecem um cartão e um número de identificação pessoal (senha). Dê exemplos de requisitos de confidencialidade, integridade e disponibilidade associados com esse sistema e, em cada caso, indique o grau de importância desses requisitos.

#### Resposta:

Confidencialidade:

Manter em sigilo dados sensíveis como saldo, informações do usuário, dados do cartão e senha.

Então o grau de importância é alto, já que deve restringir acesso conforme a LGPD para evitar danos financeiros.

Integridade:

Prevenir alterações não autorizadas no saldo e no histórico de transações.

Contém alto grau de importância, pois é necessário garantir que as transações financeiras sejam seguras contra ataques e manipulações.

Disponibilidade:

Possibilitar acesso rápido e confiável à conta do usuário.

Possui alto grau de importância, pois deve assegurar velocidade moderada/alta e confiabilidade na autenticação e apresentação de dados.

## 7.Para responder as letras abaixo, por favor, consulte o livro-texto da disciplina:
### (a) Desenhe uma matriz similar ao Quadro 1.4 que mostre o relacionamento entre serviços de segurança e ataques.
### (b) Desenhe uma matriz similar ao Quadro 1.4 que mostre o relacionamento entre mecanismos de segurança e ataques.

#### a) Resposta:
![Alt text](/Atividade01/Imagens/p1-atv01.png)
#### b) Resposta:
![Alt text](/Atividade01/Imagens/p2-atv01.png)