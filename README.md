# Jogo de cartas Uno

## Sobre o projeto
Esse foi um programa concluído no primeiro semestre de Ciência da Computação na UFRGS (2020/1), na disciplina de Fundamentos de Algoritmos ministrada pela professora Leila Ribeiro.

O objetivo principal desse algoritmo era acostumar o aluno com o conceito de estruturas (cartas) e listas de estruturas (mão com várias cartas). Não era necessário implementar o jogo completo e de forma dinâmica, apenas algumas funcionalidades mais pontuais.

Entretanto, fazia parte da atividade representar, mesmo que de maneira simples, as cartas do jogo. 
> Por exemplo: uma carta vermelha de número 2 deveria ser representada no mínimo por um retângulo vermelho com o número '2' posicionado em cima.

***

## Desenhando as cartas com formas geométricas da linguagem Racket
Esse foi o principal desafio de todo o programa. Mesmo que não fosse um requesito, eu quis puxar até o limite as possibilidades de desenho com as formas geométricas que o Racket fornece.
Todas as formas usadas podem ser encontradas na documentação do pacote htdp-lib na seção [Images: "image.rkt"](https://docs.racket-lang.org/teachpack/2htdpimage.html)

## Fundo das cartas
Parte simples de desenhar, usando apenas retângulos e uma elipse rotacionada:

![fundo](https://user-images.githubusercontent.com/72423032/158036035-302b8b01-9526-4798-afa1-ffec228fc81a.png)

## Números das cartas
Para fazer o número central da carta com o sombreado, basta sobrepor o número da cor desejada sobre uma cópia escura dele mesmo

![número principal](https://user-images.githubusercontent.com/72423032/158036244-fbf2fb3b-c684-4ff7-82d6-030e67bc73c7.png)

O número que aparece nos cantos da carta funciona da mesma forma, mas sempre da cor branca e em tamanho menor:

![número canto](https://user-images.githubusercontent.com/72423032/158036280-e6645ab0-e283-40e5-a452-33c6b4a6ad78.png)

## Carta comum
Juntando os dois desenhos anteriores, temos:

![cartas com números](https://user-images.githubusercontent.com/72423032/158036330-aa7a02a7-250b-42f2-b728-fe0349254f38.png)

## Cartas especiais
### Inverte
Para fazer a seta dessa carta foi necessário usar um triângulo isósceles, um retângulo e 1/4 de um círculo. Duplicando esse desenho e adicionando as sombras, podemos fazer tanto o desenho central da carta, quanto o desenho dos cantos:

![inverte](https://user-images.githubusercontent.com/72423032/158036444-509f442c-fe58-4e53-952e-3aa42bc5b4b4.png)

### Bloqueio
Nesse desenho foi preciso a junção de 2 elipses inteiras para fazer o fundo maior e sua sombra, e 4 elipses cortadas pela metade para fazer os "furos" centrais e suas sombras também:

![bloqueio](https://user-images.githubusercontent.com/72423032/158036529-eeb92c1f-c3c7-4ce0-8af8-9a74618509be.png)

### Compra +2
Essa carta possui duas cartinhas menores no seu centro, mas o principal problema é que elas estão inclinadas. Por isso foi necessário o uso de 6 triângulos escalenos para alcançar esse efeito, criando-os no formato LAL (lado, ângulo, lado):

![+2](https://user-images.githubusercontent.com/72423032/158036624-23219b3a-3f63-4b3e-8dfa-3eba898d188e.png)

### Compra +4
Após desenhar as cartinhas pequenas usadas na carta de compra +2, basta repetir o desenho quatro vezes em cores diferentes para concluir o desenho da carta de compra +4.

### Coringa
Usando 1/4 de quatro elipses de cores diferentes, é facil construir esse desenho central da corta coringa também.

Todas as cartas especiais ficam da seguinte maneira:

![cartas especiais](https://user-images.githubusercontent.com/72423032/158036776-7ad1931f-c991-4465-bd02-8fef11ef3f47.png)

### Jogo completo ilustrado

Utilizando o desenho das mãos e de uma mesa:

![mãos](https://user-images.githubusercontent.com/72423032/158036821-246352df-ba5d-437a-8d77-543571d56c7c.png)
![mesa](https://user-images.githubusercontent.com/72423032/158036824-cfc8f3d3-f71b-4efc-9e14-a231c4565216.png)

A representação de uma mão com várias cartas num jogo fica desta forma:

![jogo completo](https://user-images.githubusercontent.com/72423032/158036864-6039ba8a-116a-4c55-a52c-90d7dd88d22b.png)
