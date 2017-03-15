---
layout: post
title:  "Java 8 - Entendendo Method Reference"
date:   2016-07-10
categories: java
tags: [java, java8]
image: 
keywords:
related:
  - title: Meu post super simple sobre Lambda do Java 8.
    url: http://suelengc.com/2016/java-8-lambdas
  - title: Excelente post no blog da Caelum sobre Java 8 
    url: http://blog.caelum.com.br/o-minimo-que-voce-deve-saber-de-java-8/
  - title: Apresentação sobre Java 8 por Paulo Silveira no Conexão Java 2014
    url: https://www.youtube.com/watch?v=UZaKFZHrnag
  - title: Documentação da Oracle sobre Method Reference
    url: http://docs.oracle.com/javase/tutorial/java/javaOO/methodreferences.html
resumo: >
   Entenda para que serve e como usar os métodos de referência do Java 8. Veja também meu <a href='https://www.youtube.com/watch?v=BPootnK8taE' target='_blank'>vídeo sobre Method Reference</a> no meu canal do YouTube.  
---

Se com os [Lambdas](http://suelengc.com/2016/java-8-lambdas) as coisas ficaram muito mais legíveis no Java, os métodos de referência vieram dar um pitaco a mais de legibilidade.

Os métodos de referência vieram para simplificar os Lambdas que contém apenas uma linha de execução, então ao invés de escrevermos o Lambda escrevemos de uma forma mais simples ainda. 

Vamos pegar como exemplo o seguinte código que usa Lambda para implementar um `Comparator`.

{% highlight java %}
Collections.sort(frutas, (s1, s2) -> s1.compareTo(s2));
{% endhighlight %}

Este código com *method reference* ficaria assim:

{% highlight java %}
Collections.sort(frutas, String::compareTo);
{% endhighlight %} 

No caso acima, estamos usando a regra de uso do *method reference* onde chamamos um **método de instância**, ou seja, o método `compareTo` só poderia ser usado com uma instância de `String`, porém a partir da classe** ao invés do objeto. 

Nesta situação o compilador é capaz de inferir que as duas strings que seriam passadas no método `compare` da implementação de `Comparator` devem ser passadas como `s1.compareTo(s2)`.




