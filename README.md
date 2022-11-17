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
