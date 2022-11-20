# css-only

# O que é o css?

Css é a estilização de uma pagina css, ou seja! ele atua sobre o HTML dando vida em "simples" tags com cores, tamanho e deixando ela dinamica.

# Css básico

Como incluir css em nossas paginas HTML?

Temos 3 formas de adicionar css em nossas paginas HTML.

- inline
- interno (dentro da tag style)
- externo (importando)

Qual devemos usar?

Para termos uma usabilidade melhor e para poder reaproveitar os códigos usamos o externo.

<b>style.css</b>

# Seletores

Seletores são a forma como selecionamos os elementos do html para modificar.

- Seletores de Tipo: onde marcamos diretamente as tags que queremos selecionar, exemplo p para selecionar todo <p>.
- Pseudo-elementos: como o nome sugere, eles não são elementos em si, mas servem para selecionar parte do html relativo a outro seletor. Por exemplo, p::first-letter.
- Seletores de Classe: um dos que mais utilizamos, podemos atribuir classes para diferentes elementos e então selecionar essas classes. Exemplo: <p class="text"> pode ser selecionado com .text.
- Seletores de atributo: selecionamos elementos com um tipo específico de atributo. Por exemplo, input[type='number']. Aqui estamos selecionando todos os inputs que tiverem type=number como atributo.
- Pseudo-classes: selecionamos elementos baseados em seus estados CSS. Por exemplo :hover, :active, :checked e outros.
- Seletores de Id: selecionamos um elemento pela sua Id única. Só pode existir um único elemento para cada id. Exemplo: <h1 id="header"> seria selecionado com #header.
- Estilos inline: são estilos aplicados diretamente ao elemento, através do atributo style. Por exemplo, <h1 style="font-size: 16px">

## especificidade

Os pesos de cada seletor

- Peso mais baixo: seletores de tipo e pseudo-elementos
- Peso baixo: classe, atributo e pseudo-classes
- Peso médio: seletores de id
- Peso alto: estilos inline

1. Se estilos de diferentes pesos são aplicados a um mesmo elemento, o estilo que tiver o maior peso será o aplicado. Se os estilos tiverem o mesmo peso, os estilos que vierem mais abaixo, serão os aplicados. Isso é devido ao "efeito cascata" que dá exatamente o nome do CSS (Cascading Style Sheets).

```css:
// <h1 class="foo bar">

.foo {
  color: green;
}

.bar {
  color: red; // essa será a cor aplicada
}
```

2. Quando dois seletores de mesmo peso são aplicados a um elemento, é contado como 2x o peso. Por exemplo, elementos com duas classes aplicadas terão um peso maior do que um elemento com só uma classe.

```css:
.foo.bar {
  color: blue; // essa será a cor aplicada
}

.bar {
  color: red;
}
```

3. Estilos de peso maior sempre irão prevalecer, não importa quantos elementos você colocar.

Exemplo com id:

```css:

#footer {
background: red; // essa será a cor aplicada
}

div.class1.class2.class3.class4 {
background: blue;
}

```

# Combinando seletores

No css podemos combinar multiplos seletores para que ele fique mais especifico e modifique apenas aquela seleção.

1. irmão adjacentes

- São irmãos proximos (um abaixo do outro) que compartilham o mesmo pai.
- Apenas o segundo elemento (após o sinal de +) será modificado

h2 + p {

}

![exemplo-irmaos-adjacentes](./img/Captura%20de%20tela%20de%202022-11-20%2010-57-38.png)

2. Irmão geral

- Modifica o irmão mesmo que tenha outros elementos proximos
- Apenas o segundo elemento (após o sinal de +) será modificado

h2 ~ p {

}

![exemplo-irmaos-geral](./img/Captura%20de%20tela%20de%202022-11-20%2011-04-40.png)

3. Filho

- Modifica o segundo elemento somente se for um filho direto (que está dentro do pai)

div > p {

}

![exemplo-filho-direto](./img/Captura%20de%20tela%20de%202022-11-20%2011-08-52.png)

4. Decendentes

- Modifica o segundo elemento mesmo que não não seja um filho direto

div p {

}

![exemplo-filho-direto](./img/Captura%20de%20tela%20de%202022-11-20%2011-12-46.png)

# Propriedades e Valores CSS

No css temos propriedades que alteram de alguma forma a estilização dos nossos sites.

Exemplos:

- color
- margin
- display

Todas essas propriedades são especificas do css e que recebem um determinado valor, alterando as caracteristicas quando aplicadas.

Já os valores complementam as propriedades de forma especifica.

- red
- 10px
- block

# Box-Model

Tudo que escrevemos no HTML são "caixas" e vamos aprender como modificar a Altura, largura e como essas caixas se comportam quando alteradas pelo css.

Nossas "caixas" são compostas pelas seguintes caracteristicas.

- Content (conteudo)
  Content é o conteudo que incluimos dentro de alguma tag, seja um texto , uma imagem ou um audio por exemplo.

- Padding
  Padding é o espaçamento interno entre a conteudo e a borda

- Border
  Borda como o nome já diz é a borda que envolve o conteudo, toda caixa tem borda, mas só vemos se atribuirmos valores para ela.

- Margin
  Já a Margin é a distancia entre uma caixa e outra.

<b>As propriedades Padding e Borda ao serem atribuidas, aumentam o tamanho da caixa</b>

Como arrumamos isso?

No css temos uma propriedade que ajusta o tamanho da caixa para que a largura + altura + padding + borda tenha o tamanho setado para aquela caixa.

```css:

#body {
box-sizing: border-box;
}

```

# Displays

Essa propriedade modifica o direcionamento dos elementos HTML, no css temos elementos inlines e block.

- Display Inline

Transforma os elementos em inline ou seja um do lado do outro e a largura do seu elemento é determinada pelo tamanho do conteudo.

Obs: Propriedades inline não aceita modificação de altura do elemento.

- Display block

Transforma os elementos em block, que ocupam a largura total e joga os outros elementos para baixo.

Obs: Aceita altura e largura

- Display inline-block

Une os dos display anterior, mantem os elementos um ao lado do outro mas agora aceitando as caracteristicas de block, onde podemos setar altura e largura.

## Arquitetura Css

# Padrão BEM

BEM é uma convenção de nomes na estilização de CSS, que usa como regra, bloco,elemento e modificador(BEM).

- bloco

Os blocos no padrão BEM é a estrutura da nossa aplicação, como por exemplo:

header , menu , container

- .menu
- .container

<hr>

- elementos
  Já os elementos são os "filhos" desses blocos,omo por exemplo:

- .menu\_\_item
- .menu\_\_link

imagem, lista, titulo.

<hr>

- modificador

é uma variação do elemento, ou seja caso eu tenha uma estilização espefifica de um link comparado aos demais.

verificar a necessidade de ter um modificador caso seja algo simples/unico

- menu--dark
- menu\_\_link--dark

<hr>
## :bulb: dicas

```html:

<article class="card">
  <div class="card__header">
    <h1 class="card__header__titulo"></h1>
    </div>

</article>

```

não precisa ser um padrão tão verboso, caso o elemento não seja filho diretamente , podemos aplicar somente o bloco inicial e especificar o elemento.

```html:

<article class="card">
  <div class="card">
    <h1 class="card__titulo"></h1>
    </div>

</article>

```
