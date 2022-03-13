**UNIVERSIDADE LUSÓFONA DE HUMANIDADES E TECNOLOGIAS**

*Linguagens de Programação I*

# Exercício 2 - Idade e Categorias

Este exercício serve os seguintes objectivos:
- Utilização de alguns condições
- Utilização de operadores
- Utilização de variáveis
- Praticar pensamento algoritmico

Na resolução destes exercícios deve ser utilizada a Linguagem de Programação C. Para além da correta implementação dos requisitos, tenha em conta os seguintes aspetos:
- O código apresentado deve ser bem indentado. 
- O código deve compilar sem erros ou *warnings* utilizando o *gcc* com as seguintes flags:
- `-g -Wvla -Wall -Wpedantic -Wextra -Wdeclaration-after-statement`
- Tenha em atenção os nomes dados das variáveis, para que sejam indicadores daquilo que as mesmas vão conter.
- O trabalho deve ser desenvolvido e submetido de forma individual.

Este exercício deverá ser submetido na plataforma Pandora até às 23:59 do dia 20/3/2022 e será contabilizado para a nota final da unidade curricular de acordo com os critérios disponibilizados na página da disciplina, concretamente nos slides da primeira aula.

## Descrição

Num campeonato de Wakeboard os atletas são divididos por categorias. A categoria do atleta depende da sua idade no dia 31/12 do ano em que decorre o campeonato. As categorias são as seguintes:

| Categoria | Sigla | Descrição                   |
|-----------|-------|-----------------------------|
| Sub 14    | U14   | 14 anos ou inferior a 31/12 |
| Sub 18    | U18   | 18 anos ou inferior a 31/12 |
| Open      | O     | sem restrições de idade     |
| Masters   | O30   | 30 anos ou mais a 31/12     |
| Veterans  | O40   | 40 anos ou mais a 31/12     |

Porém, no momento em que o atleta se inscreve na competição, pode escolher em qual categoria vai competir dentro da lista de categorias possíveis para a sua idade. A regra é que um atleta pode sempre competir numa categoria de dificuldade superior, mas nunca pode competir numa categoria de dificuldade inferior. Sendo assim:
- Um atleta Sub 14 pode competir em Sub 14, Sub 18 ou Open
- Um atleta Sub 18 pode competir em Sub 18 ou Open
- Um atleta Open só pode competir em Open
- Um atleta Master pode competir em Masters ou Open
- Um atleta Veteran pode competir em Veterans, Masters ou Open

Pretende desenvolver-se um programa que seja capaz de determinar a idade de um atleta, a sua categoria, e apresentar a lista de categorias em que o atleta se pode inscrever.

## Detalhes de implementação

O programa começa por lêr do teclado um caracter e 6 inteiros. O caracter serve para escolher qual o output a apresentar:
- 'a' - idade
- 'c' - categoria
- 't' - idade, categoria e lista de categorias onde se pode inscrever

Os 6 inteiros correspondem a dia, mês e ano de nascimento e dia, mês e ano atual. Atenção que o programa não imprime nada no ecrã até que sejam lidos os inputs do utilizador. Em seguida, o programa faz os cálculos necessários e apresenta o resultado no terminal. Após apresentar o resultado, o programa deve simplesmente terminar.

### Opção 'a'
O programa deverá devolver a idade do atleta imprimindo no terminal a mensagem:

```AGE: <valor>\n```

onde `<valor>` deve ser substituido pela idade em anos do atleta.

Exemplo:
```bash
a 05 03 2000 01 03 2022
AGE: 21
```

### Opção 'c'
O programa deverá imprimir a categoria natural do atleta consoante a sua idade. Ou seja, é necessário determinar a idade do atleta ao dia 31/12 do ano actual e depois, com base nessa informação, é necessário determinar qual a categoria onde melhor se insere. Deverá depois imprimir a mensagem:

```CATEGORY <categoria>\n```

onde `<catetoria>` deverá ser a sigla que representa a categoria do atleta - U14, U18, O, O30 ou O40.

Exemplo:
```bash
c 06 08 2015 01 03 2022
CATEGORY U14
```

### Opção 't'


O programa deverá mostrar a idade do atleta, a categoria dele a lista de categorias onde o atleta pode competir. O programa deve mostrar a seguinte mensagem:

```
AGE: <idade>
CATEGORY <cat>
POSSIBLE CATEGORIES:
<cat>
<cat1>
<cat2>
```
Onde `<idade>` deve ser substituido pela idade em anos do atleta; `<cat>` deve ser substituido pela sigla correspondente à categoria do atleta, e `<cat1>` e `<cat2>` são as categorias onde o atleta pode competir. Exemplo:

```bash
t 05 04 2016 02 03 2022
AGE: 5
CATEGORY U14
POSSIBLE CATEGORIES:
U14
U18
O
```

```bash
t 20 08 2000 01 01 2022
AGE: 21
CATEGORY O
POSSIBLE CATEGORIES:
O
```

## Mensagens de erro

O programa deverá começar por verificar se a opção introduzida é válida. Caso o utilizador introduza uma opção que não é uma das opções válidas, o programa deverá imprimir a mensagem ```Opcao invalida\n``` e em seguida deverá terminar sem fazer mais operações.

Em seguida o programa deverá verificar a validade das datas fornecidas: 
- verificar a data de nascimento
- verificar a data actual
- verificar a data actual é inferior à data de nascimento.
Se qualquer uma destas verificações falhar, o programa deve imprimir no terminal a mensagem ```Invalid date``` e em seguida deve terminar.

O programa deverá terminar imediatamente após um dos critérios de validação falhar. Ou seja, caso a data de nascimento seja inválida, o programa não vai verificar as outras datas. Simplesmente deverá terminar.

Nota 1: Considera-se o dia inválido se for menor que 1 ou superior ao numero máximo de dias de cada mês. O programa deverá também validar as datas relativamente aos dias de cada mês e especialmente em relação aos dias do mês de fevereiro. Para isso deverá tomar em consideração se o ano é bissexto ou não. 

Nota 2: Anos bissextos são múltiplos de 4. Anos que também são múltiplos de 100 não são bissextos (1900 não é bissexto). Mas anos que são multiplos de 4, 100 e 400 são bissextos (2000 é bissexto).

## Honestidade Académica

Nesta disciplina, espera-se que cada aluno siga os mais altos padrões de honestidade académica. Trabalhos que sejam identificados como cópias serão anulados e os alunos envolvidos terão nota zero - quer tenham copiado, quer tenham deixado copiar.
Para evitar situações deste género, recomendamos aos alunos que nunca partilhem ou mostrem o seu código.
A decisão sobre se um trabalho é uma cópia cabe exclusivamente aos docentes da unidade curricular.
Os alunos são encorajados a discutir os problemas com outros alunos mas não deverão, no entanto, copiar códigos, documentação e relatórios de outros alunos. Em nenhuma circunstância deverão partilhar os seus próprios códigos, documentação e relatórios. De facto, não devem sequer deixar códigos, documentação e relatórios em computadores de uso partilhado.

*Todos os entregues serão comparados utilizando um algoritmo de detecção de plágio [(3)](#ref3) que automaticamente atribui uma percentagem de semelhança entre os trabalhos. Este algoritmo é extremamente robusto e será utilizado nesta disciplina em todos os trabalhos ao longo do ano.* 

## Referências

<a name="ref1"></a>

* (1) Pereira, A. (2017). C e Algoritmos, 2ª edição. Sílabo.

<a name="ref2"></a>

* (2)  PANDORA - Yet Another Automated Assessment Tool, https://saturn.ulusofona.pt/.

<a name="ref3"></a>

* (3)  Saul Schleimer, Daniel S. Wilkerson, and Alex Aiken. 2003. Winnowing: local algorithms for document fingerprinting. In Proceedings of the 2003 ACM SIGMOD international conference on Management of data (SIGMOD '03). Association for Computing Machinery, New York, NY, USA, 76–85. DOI:https://doi.org/10.1145/872757.872770

## Metadados

* Autor: [Pedro Serra]
* Instituição: [Universidade Lusófona de Humanidades e Tecnologias][ULHT]


