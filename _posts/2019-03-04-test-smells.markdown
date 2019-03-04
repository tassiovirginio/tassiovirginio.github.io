---
title:  "Test Smells"
date:   2019-03-04 11:00
categories: [smells, tests]
tags: [smells,tests, java, junit]
published: true
---

Olá pessoas... 

Hoje vou falar um pouco sobre Test Smells, o que são e quais os principais identificados nos textos acadêmicos.

Antes de descrever o que são Test Smells, tenho que explicar primeiramente o que é um code smells (ou bad smell ou somente smell) no desenvolvimento de software. Tem determinou o termo foi o Martin fowler em seu livro "Refatoração" com ajuda de Kent Beck. Nesse livro Fowler descreve o que são e como detectar uma lista de Smells, que são "antipadrões" nos códigos, especificamente nesse livro na linguagem Java (mas na sua maioria são genéricos).

Em seu artigo "Refactoring Test Code" de 2001, Arie van Deursen, ele percebeu que a refatoração de códigos de produção e de testes tinham seus próprios conjuntos de smells, realizou um levantamento dos smells que podemos encontrar em códigos de teste, e os modos de refatoração. Com esse estudo foram determinado o termo Test Smells.

A lista que iremos apresentar é com base nesse artigo de Deursen.

# Test Smells

- Mystery Guest
Um teste usa recursos externos (por exemplo, arquivo contendo dados de teste). Podendo ocasionar em dificuldades na compreensão do teste devido a valores desconhecidos.
<br>

- Resource Optimism
Um teste faz suposições sobre o estado / existência de recursos externos. Possível efeito: Resultado não determinístico dependendo do estado dos recursos.
<br>

- Test Run War
Um teste aloca recursos (por exemplo, arquivos tmp) também usados por outras pessoas.Possível efeito: Falhas ocorrem quando várias pessoas executam testes simultaneamente. Uma maneira de refatorar é tornar o recurso exclusivo. 
<br>

- General Fixture
Um dispositivo de teste é muito geral e os métodos de teste só acessam uma parte dele. Exemplo: uma classe JUnit tendo pelo menos um método não utilizando de modo inteiro test fixture definido no método setUp(). 
<br>

- Eager Test
Um método de teste verifica vários métodos do objeto testado. Efeito possível: Dificuldades na compreensão e manutenção de testes. Refatoração: Extrair método.
<br>

- Lazy Test
Vários métodos de teste verificando um método da classe testada usando os mesmos parâmetros.
<br>

- Assertion Roulette
Ocorre quando um método de teste tem múltiplas asserções não documentadas. Várias declarações de asserção em um método de teste sem uma mensagem descritiva afetam a legibilidade / facilidade de compreensão / manutenção, pois não é possível entender o motivo da falha do teste.
<br>

- Indirect Testing
Um teste interage com a classe sendo testada indiretamente por meio de outro objeto.
<br>

- For Testers Only
Uma classe de produção contém métodos usados apenas por métodos de teste.
<br>

- Sensitive Equality
O método toString é usado em instruções de Assertions. Efeito possível: Falhas podem ocorrer se o método toString for alterado.
<br>

- Test Code Duplication
Pedaços (cópias) de código de produção contidos dentro dos testes unitários. Efeito possível: Cópias de código têm efeitos negativos na manutenção.
<br>

Essa lista é uma coletânea inicial dos test smells, atualmente já foram identificados outros na literatura cinza (blogs, revistas). Posteriormente irei enriquecer com mais detalhes e novos smalls essa página. Atualmente ela só tem o intuito de apresentar superficialmente o que são so test smells e sua origem.