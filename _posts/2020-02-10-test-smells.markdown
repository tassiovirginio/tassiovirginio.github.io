---
title:  "Test Smells"
date:   2019-03-04 11:00
categories: [smells, tests]
tags: [smells,tests, java, junit]
published: true
---
Test Smells, o que são e quais os principais identificados nos textos acadêmicos.

Antes de descrever o que são Test Smells, tenho que explicar primeiramente o que é um code smells (ou bad smell ou somente smell) no desenvolvimento de software. Tem determinou o termo foi o Martin fowler em seu livro "Refatoração" com ajuda de Kent Beck. Nesse livro Fowler descreve o que são e como detectar uma lista de Smells, que são "antipadrões" nos códigos, especificamente nesse livro na linguagem Java (mas na sua maioria são genéricos).

Em seu artigo "Refactoring Test Code" de 2001, Arie van Deursen, ele percebeu que a refatoração de códigos de produção e de testes tinham seus próprios conjuntos de smells, realizou um levantamento dos smells que podemos encontrar em códigos de teste, e os modos de refatoração. Com esse estudo foram determinado o termo Test Smells.

A lista que iremos apresentar é com base nesse artigo de Deursen.

### Lista - Test Smells

- Mystery Guest<br>
Um teste usa recursos externos (por exemplo, arquivo contendo dados de teste). Podendo ocasionar em dificuldades na compreensão do teste devido a valores desconhecidos.
<br>

- Resource Optimism<br>
Um teste faz suposições sobre o estado / existência de recursos externos. Possível efeito: Resultado não determinístico dependendo do estado dos recursos.
<br>

- Test Run War<br>
Um teste aloca recursos (por exemplo, arquivos tmp) também usados por outras pessoas.Possível efeito: Falhas ocorrem quando várias pessoas executam testes simultaneamente. Uma maneira de refatorar é tornar o recurso exclusivo. 
<br>

- General Fixture<br>
Um dispositivo de teste é muito geral e os métodos de teste só acessam uma parte dele. Exemplo: uma classe JUnit tendo pelo menos um método não utilizando de modo inteiro test fixture definido no método setUp(). 
<br>

- Eager Test<br>
Um método de teste verifica vários métodos do objeto testado. Efeito possível: Dificuldades na compreensão e manutenção de testes. Refatoração: Extrair método.
<br>

- Lazy Test<br>
Vários métodos de teste verificando um método da classe testada usando os mesmos parâmetros.
<br>

- Assertion Roulette<br>
Ocorre quando um método de teste tem múltiplas asserções não documentadas. Várias declarações de asserção em um método de teste sem uma mensagem descritiva afetam a legibilidade / facilidade de compreensão / manutenção, pois não é possível entender o motivo da falha do teste.
<br>

- Indirect Testing<br>
Um teste interage com a classe sendo testada indiretamente por meio de outro objeto.
<br>

- For Testers Only<br>
Uma classe de produção contém métodos usados apenas por métodos de teste.
<br>

- Sensitive Equality<br>
O método toString é usado em instruções de Assertions. Efeito possível: Falhas podem ocorrer se o método toString for alterado.
<br>

- Test Code Duplication<br>
Pedaços (cópias) de código de produção contidos dentro dos testes unitários. Efeito possível: Cópias de código têm efeitos negativos na manutenção.
<br>

São apresentados novos test smells no estudo de Meszaros, Smith e Andrea (2003), os quais apresentamos a seguir:

 - Can’t See the Forest for the Trees<br>
 Possui muito código de teste, o qual dificulta entender o quê o teste está verificando. Os testes não agem como uma especificação porque demoram muito para serem entendidos.
<br>

 - Complex Undo Logic<br>
O código complexo de desmontagem do teste aumenta a probabilidade de deixar o ambiente de teste corrompido por não ser limpo corretamente. Isso resulta em "vazamentos de dados" que, posteriormente, podem fazer com que esse ou outros testes falhem sem motivo aparente.
<br>

 - Complex Test Code/Verbose Test<br>
 Excesso de código de teste ou Lógica de Teste Condicional (Conditional Test Logic). Difícil verificar a exatidão dele e mais propensos a conter erros.
<br>

 - Conditional Test Logic<br>
 Testes contendo lógica condicional (instruções IF ou loops).
<br>

 - Magic Numbers ou Hard Coded Test Data<br>
Muitos "Números Mágicos" ou Strings usados ao criar objetos que provavelmente resultam em um Teste Irrepetível.
 <br>

- Fragile Tests<br>
Toda vez que você altera o SUT, os testes não são compilados ou eles falham. Você precisa modificar muitos testes para tornar as coisas "verdes" novamente. Isso aumenta muito o custo de manutenção do sistema.
<br>

- Fragile Fixture<br>
Os testes começam a falhar quando um dispositivo compartilhado é modificado (por exemplo, novos registros são colocados no banco de dados). Isso ocorre porque os testes estão fazendo suposições sobre o conteúdo do dispositivo compartilhado.
<br>

- Interdependent Tests/Dependent Test<br>
Quando um teste falha, vários outros testes falham sem motivo aparente, porque dependem dos efeitos colaterais de um teste executado anteriormente. Os testes não podem ser executados sozinhos e são difíceis de manter.
<br>

- Unrepeatable Tests<br>
Os testes não podem ser executados repetidamente sem intervenção manual. Isso é causado por testes que não são limpos após sua execução e impedem que eles ou outros testes sejam executados novamente.
<br>

Peruma também apresentou alguns novos tipos de test smells em seu estudo, que são:

- Constructor Initialization<br>
Métodos de teste que apresentam um construtor. Idealmente, o conjunto de testes não deve ter um construtor. A inicialização dos campos deve estar no método setUp(). Os desenvolvedores que desconhecem o objetivo do método setUp() permitiriam esse test smell criando um construtor para o conjunto de testes.
<br>

- Default Test<br>
Por padrão, o uma IDE cria classes de teste padrão quando um projeto é criado. Essas classes de teste de modelo devem servir como um exemplo para os desenvolvedores ao escrever testes de unidade e devem ser removidas ou renomeadas. A presença desses arquivos no projeto fará com que os desenvolvedores comecem a adicionar métodos de teste a esses arquivos, tornando a classe de teste padrão um contêiner de todos os casos de teste e violando as boas práticas de teste. Os problemas também surgiriam quando as classes precisassem ser renomeadas no futuro.
<br>

- Duplicate Assert<br>
Esse smell ocorre quando um método de teste testa a mesma condição várias vezes no mesmo método de teste.
<br>

- Empty Test<br>
Métodos de teste que não contêm instruções executáveis.
<br>

- Exception Handling<br>
Esse cheiro ocorre quando a aprovação ou reprovação de um método de teste depende explicitamente do método de produção que gera uma exceção.
<br>

- Ignored Test<br>
A partir do JUnit 4 é fornecido aos desenvolvedores a capacidade de impedir a execução de métodos de teste. No entanto, esses métodos de teste ignorados resultam em sobrecarga no que diz respeito ao tempo de compilação e um aumento na complexidade do código e no tempo de compreensão.
<br>

- Redundant Print<br>
As instruções de impressão nos testes de unidade são redundantes, pois os testes de unidade são executados como parte de um script automatizado. Podendo consumir recursos ou aumentar o tempo de execução.
<br>

- Redundant Assertion<br>
Esse smell ocorre quando os métodos de teste contêm declarações de asserção sempre verdadeiras ou falsas. Um teste destina-se a retornar um resultado binário, independentemente de o resultado pretendido estar correto ou não, e não deve retornar a mesma saída, independentemente da entrada.
<br>

- Sleepy Test <br>
Os desenvolvedores introduzem esse cheiro quando precisam pausar a execução de instruções em um método de teste por um certo período e continuar a execução.
<br>

- Unknown Test <br>
Um método de teste sem uma condição de asserção, o teste sempre vai dar como válido, não resultando em uma exceção. Essa prática de programação dificulta a compreensibilidade do teste.
<br>


Essa lista é uma coletânea inicial dos test smells, atualmente já foram identificados outros na literatura cinza (blogs, revistas). Posteriormente irei enriquecer com mais detalhes e novos smalls essa página. Atualmente ela só tem o intuito de apresentar superficialmente o que são so test smells e sua origem.