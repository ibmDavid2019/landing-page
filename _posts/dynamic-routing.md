---
title: 'Como estender protótipos com JavaScript'
excerpt: 'Um dos pontos ideológicos do primeiro framework JavaScript foi a extensão de protótipos versus funções de encapsulamento.'
coverImage: '/assets/blog/dynamic-routing/cover.jpg'
date: '2022-10-31T05:35:07.322Z'
author:
  name: David Noronha
  picture: '/assets/blog/authors/jj.jpeg'
ogImage:
  url: '/assets/blog/dynamic-routing/cover.jpg'
---

Um dos pontos ideológicos do primeiro framework JavaScript foi a extensão de protótipos versus funções de encapsulamento. Frameworks como MooTools e Prototype estenderam protótipos enquanto jQuery e outros frameworks menores não. Cada um teve seus benefícios, mas, no final, todos esses anos depois, ainda acredito que a capacidade de estender protótipos nativos é um recurso enorme do JavaScript. Vamos verificar como é fácil capacitar cada instância de um primitivo estendendo protótipos!

Todo JavaScript nativo, como Number, String, Array, Object, etc. tem um prototype. Cada método em a prototypeé herdado por cada instância desse objeto. Por exemplo, podemos fornecer Arraya cada instância um uniquemétodo estendendo seu protótipo:

Matriz . protótipo . unique =  function ( )  { 
  return  [ ... new  Set ( this ) ] ; 
}

[ '1' ,  '1' ,  '2' ] . único ( ) ;  // ['1', '2'] 
new  Array ( '1' ,  '1' ,  '2' ) . único ( ) ;  // ['1', '2']
Observe que, se você também puder garantir a capacidade de encadeamento retornando this:

[ '1' ,  '1' ,  '2' ] . único ( ) . reverso ( ) ;  // ['2', '1']
A maior crítica à extensão de protótipos sempre foi a colisão de nomes onde a eventual implementação da especificação é diferente da implementação do framework. Embora eu entenda esse argumento, você pode combatê-lo com nomes de funções de prefixo. Adicionar superpoderes a um protótipo nativo para que cada instância o tenha é tão útil que eu nunca diria a alguém para não estender um protótipo. #MooToolsFTW.
