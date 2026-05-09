[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/zHqjFsRx)
# Diagnóstico de retomada - Teoria da Computação

Esta atividade serve para mapear o que você já domina sobre linguagens formais, autômatos, gramáticas e computabilidade.

Responda individualmente. Use suas palavras. Se usar IA depois da primeira tentativa, registre o uso na seção 7.

## 1. Mapa do que eu lembro

Marque cada tópico como: lembro bem, lembro parcialmente, não lembro, nunca vi ou não tenho certeza.

- alfabeto: lembro parcialmente
- cadeia: lembro parcialmente
- linguagem: lembro parcialmente
- gramática: lembro parcialmente
- autômato finito: lembro parcialmente
- linguagem regular: não lembro
- linguagem livre de contexto: nunca vi ou não tenho certeza
- linguagem sensível ao contexto: nunca vi ou não tenho certeza
- linguagem irrestrita: nunca vi
- hierarquia de Chomsky: nunca vi
- computabilidade: nunca vi
- máquina de Turing: lembro parcialmente

## 2. Definições com exemplo

Explique, com suas palavras e com um exemplo simples, usando o alfabeto `Sigma = {a, b}`.

1. O que é um alfabeto? conjuto finito e não vazio de símbolos ou caracteres
exemplo: Alfabeto binario `Sigma = {0,1}`
2. O que é uma cadeia? sequência finita e ordenada de símbolos escolhidos a partir  de um conjuto finito  chamado alfabeto
exemplo: `sigma = {ab}, sigma = {aab}`
3. O que é uma linguagem? conjunto de cadeias formadas por símbolos, apartir de um alfabeto específico e estruturado por regras rígidas
exemplos: `sigma = {a, ab, aba, abb}`
4. O que é uma gramática? é formalismo matematico que define regras para gerar todas as cadeias válidas de uma linguagem formal
exemplo: `sigma = { S -> aS | b}`


## 3. Linguagens

Considere as linguagens:

```text
L1 = { w em {0,1}* | w termina com 01 }
L2 = { a^n b^n | n >= 0 }
L3 = { a^n b^n c^n | n >= 0 }
```

Para cada linguagem:

1. escreva três palavras que pertencem à linguagem; 
2. escreva duas palavras que não pertencem;
3. diga, se souber, em qual classe ela provavelmente se encaixa;
4. explique o motivo em linguagem simples.

não sei, não me recordo de ver isso em sala de aula

Não há problema em dizer "não sei". Nesse caso, escreva o que te deixou em dúvida.

## 4. Autômato finito

Considere o autômato abaixo, sobre o alfabeto `{0,1}`:

```text
Estados: q0, q1, q2
Estado inicial: q0
Estado final: q2

Transições:
q0 --0--> q1
q0 --1--> q0
q1 --0--> q1
q1 --1--> q2
q2 --0--> q1
q2 --1--> q0
```

Responda:

1. Qual linguagem esse autômato parece reconhecer?
Para chegar em q2, passa por q1 lendo em 1}
Para chegar em q1, precisa ler 0
Padrao aceito é terminar com 01

2. Execute manualmente as cadeias abaixo e diga se aceita ou rejeita:
- `01`
   Começa em q0
   Lê 0 → q0 --0--> q1
   Lê 1 → q1 --1--> q2
   Terminou em q2 → ACEITA
  
- `101` 
   Começa em q0
   Lê 1 → q0 --1--> q0
   Lê 0 → q0 --0--> q1
   Lê 1 → q1 --1--> q2
   Terminou em q2 → ACEITA
  
- `100`
   Começa em q0
   Lê 1 → q0 --1--> q0
   Lê 0 → q0 --0--> q1
   Lê 0 → q1 --0--> q1
   Terminou em q1 → REJEITA
- `1101`
   Começa em q0
   Lê 1 → q0 --1--> q0
   Lê 1 → q0 --1--> q0
   Lê 0 → q0 --0--> q1
   Lê 1 → q1 --1--> q2
   Terminou em q2 → ACEITA
- `111`
   Começa em q0
   Lê 1 → q0 --1--> q0
   Lê 1 → q0 --1--> q0
   Lê 1 → q0 --1--> q0
   Terminou em q0 → REJEITA
   
3. Monte uma tabela curta mostrando o caminho dos estados para pelo menos duas cadeias.
 # Seção 4 — Tabela de Estados

## Cadeia `101` — ACEITA

| Passo | Símbolo lido | Estado atual | Próximo estado |
|-------|-------------|--------------|----------------|
| 1     | 1           | q0           | q0             |
| 2     | 0           | q0           | q1             |
| 3     | 1           | q1           | q2             |
| —     | fim         | q2           | **ACEITA **   |

## Cadeia `100` —  REJEITA

| Passo | Símbolo lido | Estado atual | Próximo estado |
|-------|-------------|--------------|----------------|
| 1     | 1           | q0           | q0             |
| 2     | 0           | q0           | q1             |
| 3     | 0           | q1           | q1             |
| —     | fim         | q1           | **REJEITA **  |

## 5. Gramática

Considere a gramática:

```text
S -> aS
S -> b
```

Responda:

1. Gere cinco cadeias produzidas por essa gramática.

 S → b | b |
| S → aS → ab | ab |
| S → aS → aaS → aab | aab |
| S → aS → aaS → aaaS → aaab | aaab |
| S → aS → ... → aaaaab | aaaaab 

2. Descreva a linguagem em palavras.

a linguagem é formada por qualquer quantidade de a's seguida de exatamente um b

3. Essa gramática parece regular, livre de contexto ou outra classe? Justifique de forma simples.

ela é regular, pois lado esquerdo é só S, ladon direito é terminal seguido de S ou só um gterminal

## 6. Ponto de dificuldade

Escolha um tópico da lista inicial e escreva: autonomo finito

1. o que você entende dele;  não entedia muita coisa, porem respondendo a atividade entendi como resolver as cadeias

2. onde você se confunde; nas cadeias como executar

3. que tipo de explicação ajudaria: desenho, exemplo, exercício guiado, analogia, prova passo a passo ou lista curta. exemplos detalhados e mais pratica

## 7. Uso de IA, se houver

Se você usou IA depois da primeira tentativa, registre:
usei ia para ter compreenção do conteudo da 4 e 5  pois não me recordo do contyeudo dado em, sala de aula
```text
Pergunta feita: "entregue a explicação de Automato Finito, Gramatica
Resumo da resposta:
Primeiro: entenda o autômato
Estados: q0, q1, q2
Estado inicial: q0
Estado final: q2

Transições:
q0 --0--> q1
q0 --1--> q0
q1 --0--> q1
q1 --1--> q2
q2 --0--> q1
q2 --1--> q0
Uma forma fácil de visualizar é como um mapa de navegação:

Você começa sempre em q0
Lê a cadeia símbolo por símbolo
Cada símbolo te move para outro estado
Se terminar em q2, a cadeia é aceita. Se não, é rejeitada

Como eu verifiquei: asiste uma aula no YouTube
O que eu alterei na minha resposta: apenas fiz pela forma que eu entendi
O que ainda não entendi: acho que so falta praticar 
```

## Submissão no Moodle

Depois de finalizar, copie no Moodle:

```text
Repositório:
Commit final:
Autoavaliação: nível atual, maior dificuldade e tópico que precisa ser retomado.
```
