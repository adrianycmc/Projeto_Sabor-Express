##  Curso: "Python: crie a sua primeira aplicação." - Alura.

* 3 aspas duplas ou simples também pula linha.

```python
print('''Olá mundo!''')
```

<br> 

**Input:** o usuário consegue inserir alguma coisa e interagir com a aplicação. Para converter o retorno do input de string para int, adicionamos o tipo antes de chamar o input. 

<br>

```python
opcao_escolhida = int(input('Escolha uma opção: '))
```
<br>

### Convenções para Python:
* *snake_case:* variáveis, funções e métodos;
* *PascalCase:* classes;
* *SCREAMING_SNAKE_CASE:* constantes.

A interpolação de strings pode ser feita com a inserção do f. 
```python
print(f'Você escolheu a opção {opcao_escolhida}.')
```
<br>

## Função

Imagine que você está construindo um robô que precisa fazer várias tarefas, como andar, falar e pegar objetos. Você poderia programar cada tarefa separadamente, mas seria muito trabalhoso e repetitivo.

As funções no Python são como "instruções" que você dá ao robô para realizar essas tarefas. Você define o nome da função, o que ela deve fazer e quais informações ela precisa para funcionar.

Por exemplo, você pode criar uma função chamada andar que recebe como entrada a direção e a distância que o robô deve andar.

```python
def andar(direcao, distancia):
    # Código para o robô andar na direção e distância especificadas
    print(f"O robô está andando {distancia} passos para {direcao}")
```

Depois, você pode usar essa função várias vezes, com diferentes direções e distâncias, sem precisar escrever o código da tarefa novamente.

```python
andar("frente", 10)  # O robô anda 10 passos para frente
andar("esquerda", 5) # O robô anda 5 passos para a esquerda
```

As funções facilitam a organização do código, tornando-o mais legível e reutilizável.

Você pode usar funções para:

* Organizar o código em blocos lógicos: Cada função representa uma tarefa específica, tornando o código mais fácil de entender.
* Evitar repetição de código: Você pode usar a mesma função várias vezes, com diferentes parâmetros, sem precisar escrever o código novamente.
* Criar código modular: As funções podem ser usadas em diferentes partes do programa, tornando o código mais flexível e reutilizável.

## Biblioteca `os`

A biblioteca `os` é como um "kit de ferramentas" para interagir com o sistema operacional do seu computador. Ela nos dá acesso a várias funções que permitem controlar o sistema, como:

* Criar, renomear e excluir arquivos e pastas: Imagine que você precisa organizar seus arquivos em pastas. A biblioteca os te permite fazer isso!
* Obter informações sobre arquivos e pastas: Você pode usar a biblioteca os para saber o tamanho, a data de modificação e outros detalhes sobre seus arquivos.
* Executar comandos do sistema: Lembra que usamos a função os.system('cls') para limpar o terminal? Essa função permite executar comandos do sistema operacional, como cls no Windows e clear no Mac.
* Trabalhar com caminhos de arquivos: A biblioteca os te ajuda a lidar com os caminhos dos arquivos, `como /home/usuario/Documentos/meu_arquivo.txt.`

É como se a biblioteca os fosse um "tradutor" entre o seu código Python e o sistema operacional do seu computador.

## Sintaxe do Math

Durante o projeto, fizemos uma cadeia de condicionais em que cada uma indicava uma opção do nosso aplicativo, como adicionar restaurante, listar restaurantes, ativar restaurante e finalizar o app, além de colocarmos uma condicional para caso a opção informada não fosse válida (através do uso do else).

Utilizando as instruções if elif else tivemos esse resultado:
```python
opcao_escolhida = int(input('Escolha uma opção: '))
if opcao_escolhida == 1:
    print('Adicionar restaurante')
elif opcao_escolhida == 2:
    print('Listar restaurantes')
elif opcao_escolhida == 3:
    print('Ativar restaurante')
elif opcao_escolhida == 4:
    print('Finalizar app')
else:
    print('Opção inválida!')
```
<br>
Se decidirmos utilizar a instrução match nesse caso, obteríamos o seguinte resultado:

```python
opcao_escolhida = int(input('Escolha uma opção: '))
match opcao_escolhida:
    case 1:
        print('Adicionar restaurante')
    case 2:
        print('Listar restaurantes')
    case 3:
        print('Ativar restaurante')
    case 4:
        print('Finalizar app')
    case _:
        print('Opção inválida!')
```

Perceba que recebemos a variável opção_escolhida como parâmetro da instrução match e será feito um comparativo com todos os valores determinados pelos blocos de case, e no final temos uma instrução case _, que é um padrão curinga, que corresponde a qualquer valor que não tenha sido correspondido pelos casos anteriores, ou seja, equivalente ao else da condicional anterior.

Tendo esse exemplo, podemos entender a sintaxe padrão do match. Dentro de um bloco match, você pode utilizar a instrução case para definir padrões específicos que serão comparados com a expressão que está sendo correspondida.

A estrutura básica é a seguinte:
```python
match expressão:
    case padrão_1:
        # Código a ser executado se expressão corresponder a padrão_1
    case padrão_2:
        # Código a ser executado se expressão corresponder a padrão_2
    # ... outros casos ...
    case _:
        # Código a ser executado se nenhum dos padrões anteriore
```

## `try except`

O `try except` em Python é como um "plano de contingência" para o seu código. Imagine que você está construindo uma casa e precisa de um martelo. Você tenta pegar o martelo, mas ele não está lá! O que você faz? Você procura em outro lugar, certo?

O `try except` funciona da mesma forma. Você tenta executar um bloco de código (o try) e, se algo der errado (uma exceção), você tem um plano alternativo (o except) para lidar com a situação.

Exemplo:

```python
try:
  numero = int(input("Digite um número: "))
  resultado = 10 / numero
  print(f"O resultado da divisão é: {resultado}")
except ZeroDivisionError:
  print("Erro: Divisão por zero!")
except ValueError:
  print("Erro: Você digitou um valor inválido!")
```

Neste exemplo, o código tenta converter a entrada do usuário para um número inteiro e depois divide 10 por esse número. Se o usuário digitar "0", o código gerará um ZeroDivisionError. Se o usuário digitar algo que não seja um número, o código gerará um ValueError.

O try except captura essas exceções e executa o código dentro do bloco except correspondente.

Analogia:

Imagine que você está tentando abrir uma porta. Você tenta girar a maçaneta (o try). Se a porta estiver trancada, você não consegue abri-la (uma exceção). Você então tenta abrir a porta com uma chave (o except).

## Listas

As listas são como gavetas onde você pode guardar vários objetos, como nomes de restaurantes, números, ou até mesmo outras listas!

Para criar uma lista, você usa colchetes [] e separa os itens por vírgulas. Por exemplo:

```python
frutas = ["maçã", "banana", "uva"]
```
Agora, vamos ver como adicionar, excluir e listar os itens da sua lista:

* Adicionando itens:

**append(item):** Adiciona um novo item no final da lista.

```python
frutas.append("laranja") 
print(frutas) # Saída: ['maçã', 'banana', 'uva', 'laranja']
```

**insert(índice, item):** Insere um item em uma posição específica da lista.

```python
frutas.insert(1, "abacaxi")
print(frutas) # Saída: ['maçã', 'abacaxi', 'banana', 'uva', 'laranja']
```

* Excluindo itens:

**remove(item):** Remove o primeiro item da lista que corresponde ao valor especificado.

```python
frutas.remove("banana")
print(frutas) # Saída: ['maçã', 'abacaxi', 'uva', 'laranja']
```

**pop(índice):** Remove e retorna o item na posição especificada. Se você não especificar um índice, ele remove e retorna o último item da lista.

```python
fruta_removida = frutas.pop(0)
print(frutas) # Saída: ['abacaxi', 'uva', 'laranja']
print(fruta_removida) # Saída: 'maçã'
```

* Listando itens:

**print(lista):** Imprime todos os itens da lista.

```python
print(frutas) # Saída: ['abacaxi', 'uva', 'laranja']
```

**for item in lista: :** Percorre cada item da lista e executa um bloco de código.

```python
for fruta in frutas:
    print(fruta) 
```

## Tulpas

As tuplas são estruturas de dados que nos permitem armazenar elementos de maneira ordenada e sequencial, assim como as listas. Dessa forma, ambas mantêm a ordem dos elementos e oferecem índices para acessar esses valores.

Contudo, existem diferenças fundamentais entre tuplas e listas que as tornam adequadas para diferentes situações.

Vamos entender como cada uma se comporta e quais são os cenários que devemos escolher cada tipo de estrutura:

### Sintaxe:
O primeiro ponto que diferencia esses dois arranjos é a sintaxe de cada um. Como vimos, as listas são definidas utilizando colchetes [ ], enquanto as tuplas são definidas utilizando parênteses ( ), como mostra o exemplo a seguir:

```python
lista = [1,’olá mundo’,True,9.7]
tupla = (1,’olá mundo’,True,9.7)
```
<br>

* Mutabilidade: 

A maior diferença entre essas duas configurações são suas propriedades de mutabilidade!

 <br>   

As **listas** são estruturas mutáveis, o que significa que é possível modificar seus elementos, adicionar novos itens ou remover existentes após a criação da lista, podendo inclusive utilizar funções próprias para isso como ***append(), remove(), pop(), e insert()***.

Ao contrário das listas, **tuplas são imutáveis**. Uma vez que uma tupla é criada, seus elementos não podem ser alterados, adicionados ou removidos.

* Desempenho:

Devido à sua imutabilidade, as tuplas têm um desempenho melhor do que listas para algumas operações. Elas são mais eficientes em termos de espaço e processamento em determinados cenários.

Sendo assim, listas podem ser menos eficientes em termos de desempenho para operações específicas, especialmente quando se trata de manipulação de grandes conjuntos de dados, devido à sua mutabilidade.

* Quando devo utilizar cada estrutura?

As listas são ideais quando você precisa de uma coleção de elementos que pode ser modificada ao longo do tempo. Por exemplo, ao criar uma lista de tarefas que pode ser atualizada com novos itens ou marcada como concluída.

Além disso, se você precisa adicionar, remover ou modificar elementos com frequência, as listas oferecem métodos próprios convenientes, como mencionado anteriormente. Podemos ver isso com uma lista de compras, como mostrado no código a seguir:

```python
# Criando uma lista de compras
lista_de_compras = ["Maçã", "Banana", "Leite", "Pão", "Queijo"]

# Adicionando um item à lista
lista_de_compras.append("Ovos")

# Removendo um item da lista
lista_de_compras.remove("Banana")

# Exibindo a lista
print("Lista de Compras:")
for item in lista_de_compras:
    print("- " + item)
```

Já as tuplas são apropriadas quando se deseja garantir que os elementos não sejam alterados após a criação. Isso é útil para dados que devem permanecer constantes ao longo do tempo. Como as tuplas são imutáveis, elas podem ter um desempenho ligeiramente melhor em operações de leitura e acesso a elementos. Isso também as tornam adequadas para situações em que a eficiência é crucial.

Podemos ver um exemplo de uma tupla que armazena as coordenadas geográficas de uma localização específica, que são dados imutáveis que queremos ter acesso, como mostrado a seguir:

```python
# Definindo uma tupla de coordenadas geográficas
coordenadas_gps = (40.7128, -74.0060)

# Exibindo as coordenadas
print("Coordenadas GPS:")
print("Latitude:", coordenadas_gps[0])
print("Longitude:", coordenadas_gps[1])
```

Lembre-se de sempre avaliar as condições de seu projeto e escolher qual das duas estruturas é mais adequada para cada situação.

Quer saber um pouco mais sobre Tuplas no Python? Recomendamos as seguintes leituras:

[Documentação Python - Tulpas](https://docs.python.org/pt-br/3/tutorial/datastructures.html#tuples-and-sequences)
<br>
[Tupla no Python: o que é, como criar e manipular e suas diferenças com as Listas](https://www.alura.com.br/artigos/conhecendo-as-tuplas-no-python)

## For

O laço for em Python é como um super-herói que te ajuda a realizar tarefas repetitivas de forma organizada e eficiente! Imagine que você tem uma lista de compras com vários itens e precisa adicionar cada um deles no carrinho. O for é como um ajudante que vai percorrer cada item da lista, um de cada vez, até que todos estejam no carrinho.

* Como funciona o laço for?

Ele tem a seguinte estrutura:

```python
for <variável> in <sequência>:
    # Código a ser executado para cada item da sequência
```
<variável>: É uma variável que vai receber o valor de cada item da sequência em cada iteração do laço. 
<br>
<sequência>: Pode ser uma lista, uma string, uma tupla, um dicionário ou qualquer outro objeto iterável.


Exemplo:
```python
frutas = ["maçã", "banana", "uva"]

for fruta in frutas:
    print(f"Adicionando {fruta} ao carrinho.")
```

Neste exemplo, o laço for vai percorrer cada item da lista frutas, atribuindo o valor de cada fruta à variável fruta em cada iteração. O código dentro do laço será executado para cada fruta, imprimindo uma mensagem na tela.

<br>

Imagine que estamos desenvolvendo um programa para uma aplicação de entrada de dados em que precisamos coletar informações do usuário. Uma das informações que precisamos é um número positivo, e queremos garantir que o usuário forneça um valor válido.

Nosso desafio é criar um código que solicite ao usuário que insira um número positivo. No entanto, como não podemos confiar no usuário para fornecer um valor válido na primeira tentativa, precisamos criar uma lógica que permita solicitar novamente até que o usuário finalmente insira um número válido.

Como aprendemos, podemos utilizar a estrutura de repetição for para solicitar esse valor até que essa condição seja satisfeita, como mostrado no código a seguir:

```python
numero = -1
for _ in range(3):  # Supondo um número máximo de tentativas (3) arbitrário
    numero = int(input("Digite um número positivo: "))
    if numero > 0:
        break

print("Você digitou:", numero)
```

Perceba que, para criar esse loop, precisamos definir um número arbitrário de tentativas para que o usuário inserisse esse valor. Isso acontece porque o loop for é utilizado quando se conhece previamente o número de iterações que devem ser realizadas.

Contudo, nós queremos que o usuário digite diversas vezes até que ele coloque um valor positivo e não tenha nenhuma limitação.

Neste caso, a estrutura for não consegue satisfazer o que desejamos para nosso código. E agora? O Python tem outra estrutura que podemos utilizar? A resposta é sim!

Essa linguagem oferece duas estruturas de controle de fluxo fundamentais para a execução de blocos de repetição: o for e o while. Ambas são utilizadas para a implementação de loops, permitindo que um bloco de código seja executado repetidamente enquanto determinadas condições são atendidas.

Como vimos, o loop for é utilizado quando se conhece previamente o número de iterações que devem ser realizadas. Ele é especialmente eficaz ao percorrer elementos em sequências, como listas, tuplas, strings ou ranges.

## While

O loop while, diferente do for, é utilizado quando o número de iterações não é conhecido de antemão, mas ainda assim depende de uma condição específica para manter o bloco de código em repetição. Ele continua a executar o bloco de código enquanto a condição fornecida for avaliada como verdadeira.

A sintaxe do loop while é a seguinte:

```python
while condição:
    # Bloco de código a ser repetido
```

O bloco de código dentro do while continuará a ser executado até que a condição se torne falsa, ou seja, ele apenas será executado quando a condição assumir o valor booleano de true. Isso significa que é essencial e necessário garantir que a condição eventualmente se torne falsa para evitar um loop infinito em seu projeto.

Então podemos adaptar nosso projeto anterior para utilizar o while ao invés do for, como vemos no código a seguir:
```python
numero = -1
while numero <= 0:
    numero = int(input("Digite um número positivo: "))

print("Você digitou:", numero)
```
Enquanto o número digitado for menor ou igual a zero, o programa continuará pedindo ao usuário que insira um número positivo. Quando o usuário finalmente fornecer um número positivo, o loop while será encerrado e o programa exibirá o número digitado.

Sendo assim, esse é um cenário em que um loop while é mais apropriado, pois não sabemos com antecedência quantas vezes precisaremos solicitar ao usuário que insira um número.

Ou seja, a escolha entre for e while dependerá da natureza específica do problema que você está resolvendo. Entender as nuances e aplicar a estrutura de controle de fluxo mais apropriada contribuirá para um código mais claro e eficiente a depender do seu projeto.

## Dicionário

Pense em um dicionário como um armário com gavetas. Cada gaveta tem um rótulo (a chave) e dentro dela você guarda algo (o valor). No Python, as chaves são únicas e podem ser strings, números ou até mesmo tuplas. Os valores podem ser qualquer tipo de dado, como strings, números, listas, outros dicionários e até mesmo funções!

Vamos ver alguns exemplos práticos:

* Criando um dicionário:

<br>

```python
# Criando um dicionário de informações sobre um livro
livro = {'titulo': 'O Senhor dos Anéis', 'autor': 'J.R.R. Tolkien', 'ano': 1954, 'genero': 'Fantasia'}

# Criando um dicionário de preços de produtos
precos = {'maçã': 2.50, 'banana': 1.80, 'laranja': 3.00}
```
* Acessando valores:

<br>

```python
# Acessando o título do livro
print(livro['titulo'])  # Saída: O Senhor dos Anéis

# Acessando o preço da banana
print(precos['banana'])  # Saída: 1.80
Atualizando valores:

# Mudando o autor do livro
livro['autor'] = 'J.R.R. Tolkien e Christopher Tolkien'

# Aumentando o preço da laranja
precos['laranja'] = 3.50
```

* Adicionando novos itens:

<br>

```python
# Adicionando a editora do livro
livro['editora'] = 'Martins Fontes'

# Adicionando um novo produto com o preço
precos['uva'] = 4.00
```

* Removendo itens:

```python
# Removendo o ano de publicação do livro
del livro['ano']

# Removendo o preço da banana
precos.pop('banana')
```

* Listando itens:

```python
# Listando todas as chaves do dicionário
print(livro.keys())  

# Saída: dict_keys(['titulo', 'autor', 'genero', 'editora'])

# Listando todos os valores do dicionário
print(livro.values())  

# Saída: dict_values(['O Senhor dos Anéis', 'J.R.R. Tolkien e Christopher Tolkien', 'Fantasia', 'Martins Fontes'])

# Listando todos os pares chave-valor
print(livro.items())  

# Saída: dict_items([('titulo', 'O Senhor dos Anéis'), ('autor', 'J.R.R. Tolkien e Christopher Tolkien'), ('genero', 'Fantasia'), ('editora', 'Martins Fontes')])
```

* Outros comandos úteis:

**len(dicionario):** Retorna o número de itens no dicionário.
<br>
**'chave' in dicionario:** Verifica se uma chave existe no dicionário.
<br>
**dicionario.get('chave', valor_padrao):** Retorna o valor associado à chave, ou um valor padrão se a chave não existir.
<br>
Lembre-se que os dicionários são mutáveis, ou seja, você pode modificá-los após a criação. Eles são uma ferramenta poderosa para organizar dados e são amplamente utilizados em Python.

