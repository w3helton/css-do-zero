# CSS do Zero — Guia Completo para Iniciantes

**Didática aplicada**

Este guia segue três princípios simples:

**Simplicidade:** passos curtos e diretos.  
**Prática imediata:** cada trecho de código gera mudança visual instantânea.  
**Progressão lógica:** texto → cores → caixas → layout.

Após cada exemplo, pergunte sempre:

**O que você percebe?**

Isso treina sua observação — uma habilidade essencial no desenvolvimento web.

---

# Introdução ao CSS

## O que é CSS

CSS significa **Cascading Style Sheets**.

É a linguagem responsável pela **aparência do HTML**:

- cores
    
- fontes
    
- tamanhos
    
- espaçamentos
    
- layout
    

Se o **HTML é a estrutura da casa**, o **CSS é a pintura, decoração e organização dos móveis**.

---

## Por que usar CSS

Sem CSS, uma página seria apenas texto simples.

O CSS permite:

- separar **estrutura (HTML)** de **aparência (CSS)**
    
- alterar **várias páginas com um único arquivo**
    
- melhorar **legibilidade e experiência do usuário**
    

---

# Criando sua primeira página com CSS

Antes do CSS, precisamos de um **HTML básico**.

Crie um arquivo chamado **index.html**.

```html
<!DOCTYPE html>
<html>
<head>
<title>Minha primeira página</title>
<link rel="stylesheet" href="style.css">
</head>
<body>
<h1>Meu primeiro site</h1>
<p>Este é meu primeiro parágrafo.</p>
<a href="#">Um link</a>
</body>
</html>
```
Agora crie outro arquivo chamado:

```css
style.css
```




---

# Sintaxe básica do CSS

A estrutura do CSS é simples.

```css
seletor {
  propriedade: valor;
}

Exemplo:

css

h1 {
  color: red;
}
```

- **seletor** → qual elemento será estilizado
    
- **propriedade** → o que será alterado
    
- **valor** → como será alterado
    

Salve o arquivo e atualize o navegador.

**O que você percebe?**  
O título ficou vermelho.

---

# Como funciona a Cascata do CSS

A palavra **Cascading** significa que o CSS possui **prioridades** quando duas ou mais regras se aplicam ao mesmo elemento.

Imagine a seguinte situação:

```css
p {
  color: blue;
}
.destaque {
  color: red;
}
```

```html
<p class="destaque">Texto</p>
```

Qual cor será aplicada? **Vermelha**, porque a classe `.destaque` é mais específica que o elemento `p`.

O navegador calcula a **especificidade** com um sistema de pontos:

|Seletor|Pontos (exemplo simplificado)|
|---|---|
|Estilo inline|1000|
|ID|100|
|Classe, pseudo-classe|10|
|Elemento, pseudo-elemento|1|

Na prática, a regra que vence é a de **maior pontuação**. Em caso de empate, vale a **última regra declarada** no CSS.

Além disso, existe a origem do estilo:

1. Estilo do navegador (padrão)
    
2. Estilo do usuário (raro)
    
3. Estilo do autor (você) – **ganha dos anteriores**
    
4. `!important` – **quebra a regra** (use com moderação!)
    

**Resumo para iniciantes:**

- Prefira usar **classes** para estilizar.
    
- Evite `!important`.
    
- Se algo não funcionar, verifique se não há outra regra mais específica sobrescrevendo.
    

**O que você percebe?**  
A ordem importa, mas a especificidade importa mais.

---

# FUNDAMENTOS DO CSS

Agora vamos aprender as propriedades mais usadas.

---

# Estilizando texto

## Propriedades comuns

```css
h1 {
  font-size: 32px;
  font-weight: bold;
  color: #d9534f;
}
p {
  font-size: 16px;
  line-height: 1.5;
  color: #222;
}
a {
  color: #007bff;
  text-decoration: none;
}
```

### O que cada propriedade faz

**font-size**  
Define o tamanho da fonte.

**font-weight**  
Define a espessura do texto.

**line-height**  
Controla o espaçamento entre linhas.

**text-decoration**  
Controla sublinhado e outros efeitos.

**O que você percebe?**  
O texto fica mais legível e organizado.

---

# Usando fontes externas

Uma forma simples de usar novas fontes é o **Google Fonts**.

No HTML, dentro de `<head>`:

```html
<link href="https://fonts.googleapis.com/css2?family=Roboto&display=swap" rel="stylesheet">
```

Agora no CSS:

```css

body {
  font-family: 'Roboto', Arial, sans-serif;
}
```

**O que você percebe?**  
O texto ganhou uma aparência diferente.

---

# Texto

## Alinhamento e transformação

```css
h2 {
  text-align: center;
  text-transform: uppercase;
  letter-spacing: 1px;
}
```

**text-align** → alinhamento  
**text-transform** → transforma letras  
**letter-spacing** → espaçamento entre letras

---

## Controle de quebra de texto

```css
p {
  white-space: normal;
  word-break: break-word;
}
```

Isso evita que textos longos quebrem o layout.

---

# Cores

Existem várias formas de definir cores.

### Nome

```css
color: red;
```

### Hexadecimal

```css
color: #ff0000;
```

### RGB

```css
color: rgb(255,0,0);
```

### RGBA (com transparência)

```css
color: rgba(255,0,0,0.5);
```

### HSL

```css
color: hsl(200,50%,50%);
```
Exemplo:

```css
.header {
  background-color: #e6f7ff;
  color: rgb(34,34,34);
}
```

**O que você percebe?**  
Controle preciso das cores.

---

# Background

## Imagem de fundo


```css
body {
  background-image: url('https://via.placeholder.com/1920x1080');
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
}
```

> **Dica:** Use uma imagem online (como placeholder) para testar sem precisar baixar arquivos.

---

## Gradiente

```css
.hero {
  background: linear-gradient(to bottom, #e6f7ff, #ffffff);
}
```

Gradientes substituem imagens em muitos casos.

---

# Unidades de medida

## Unidades fixas

**px** (pixels)

```css
font-size: 16px;
```

---

## Unidades relativas

**em** – relativo ao tamanho da fonte do elemento pai.

**rem** – relativo ao tamanho da fonte do elemento raiz (`html`).

```css
html {
  font-size: 16px; /* base */
}
h1 {
  font-size: 2rem; /* 32px */
}
```

---

## Unidades de viewport

**vh** – 1% da altura da tela  
**vw** – 1% da largura da tela

```css
.hero {
  height: 100vh; /* ocupa a tela inteira */
}
```

## Unidades modernas

**ch** – largura do caractere "0" da fonte. Útil para limitar largura de texto.

```css
p {
  max-width: 60ch; /* aproximadamente 60 caracteres por linha */
}
```

**clamp()** – função que define um valor flexível entre mínimo e máximo.

```css
h1 {
  font-size: clamp(1.5rem, 5vw, 3rem);
}
```

Isso faz o título crescer com a tela, mas nunca menor que 1.5rem nem maior que 3rem.

**O que você percebe?**  
Unidades relativas tornam o design mais flexível e acessível.

---

# ESTRUTURA E SELETORES

---

# Seletores

## Seletores básicos

```css

p { } /* elemento */
.classe { } /* classe */
#id { } /* id (use com moderação) */
```

---

## Seletores combinados

```css
nav ul li a { } /* descendente (espaço) */
.container > p { } /* filho direto (>) */
h2 + p { } /* irmão adjacente (+) */
h2 ~ p { } /* irmãos seguintes (~) */
```

Isso permite selecionar elementos com **grande precisão**.

---

# Pseudo-classes

Representam **estados** de elementos.

```css
a:hover {
  color: #0056b3;
}
input:focus {
  outline: 2px solid #007bff;
}
li:nth-child(odd) {
  background: #f7f7f7;
}
```

`:nth-child(odd)` seleciona itens ímpares de uma lista. Também pode ser `even` (pares) ou fórmulas como `2n+1`.

---

# Pseudo-elementos

Selecionam **partes de um elemento**.

```css
p::first-line {
  font-weight: bold;
}
p::before {
  content: "• ";
  color: red;
}
```

`::before` e `::after` inserem conteúdo antes/depois do elemento real – ótimos para ícones decorativos.

---

# O Modelo de Caixa (Box Model)

Todo elemento HTML é uma **caixa**.

![images/box model.png]
### Componentes

**content** → conteúdo (texto, imagem)  
**padding** → espaço interno, entre conteúdo e borda  
**border** → borda ao redor do padding  
**margin** → espaço externo, separa o elemento dos vizinhos

---

## Exemplo

```css
.box {
  width: 300px;
  padding: 16px;
  border: 1px solid #ccc;
  margin: 20px;
}
```

A largura total do elemento será: 300px (content) + 32px (padding left+right) + 2px (border left+right) = 334px. A margem é externa, não soma na largura total do elemento, mas afeta o espaçamento.

---
<div class="page-break">

## Box sizing: a propriedade que salva vidas

Por padrão, o CSS usa `box-sizing: content-box`, ou seja, a largura (`width`) é aplicada apenas ao **conteúdo**. Padding e border aumentam a caixa.

Isso pode tornar cálculos de layout complicados.

A solução:

```css
* {
  box-sizing: border-box;
}
```

Com `border-box`, a largura **inclui** padding e border. O conteúdo encolhe para caber dentro do tamanho definido.

**Exemplo prático:**

Sem `border-box`:

```css
.box { width: 300px; padding: 20px; } /* largura total = 340px */
```

Com `border-box`:

```css
.box { width: 300px; padding: 20px; } /* largura total = 300px, conteúdo = 260px */
```

**O que você percebe?**  
O layout fica muito mais previsível.

---

# LAYOUT

## Fluxo normal do documento

Por padrão, elementos **empilham verticalmente** na ordem do HTML:

```html
<h1>Título</h1>
<p>Parágrafo</p>
<div>Outro bloco</div>
```

Isso é chamado **fluxo normal**. Elementos de bloco ocupam toda a largura disponível e quebram linha; elementos inline (como `<a>`, `<span>`) ficam na mesma linha.

Algumas propriedades alteram esse comportamento: `position`, `float`, `display: flex`, `display: grid`.

---

# Posicionamento

## Tipos de posicionamento

- ***static*** (padrão) – segue o fluxo normal.

- ***relative*** – desloca o elemento em relação à sua posição original, mas o espaço original permanece reservado.

```css
.relative {
  position: relative;
  top: 10px;
  left: 20px;
} 
```
- ***absolute*** – Sai da posição original e gruda em um **elemento pai que tenha position** (como relative). Se não tiver nenhum, ele gruda no **canto superior esquerdo da página**.

```css
.container {
  position: relative; /* vira referência */
}
.absolute {
  position: absolute;
  top: 0;
  right: 0;
}
```
- ***fixed*** – fixo em relação à **janela do navegador**, não sai da tela ao rolar.

```css
.fixed {
  position: fixed;
  bottom: 10px;
  right: 10px;
}
```
- ***sticky*** – alterna entre `relative` e `fixed` conforme a rolagem. Útil para cabeçalhos que grudam no topo.

```css
.sticky {
  position: sticky;
  top: 0;
}
```

**O que você percebe?**  
Elementos podem sair do fluxo normal, criando sobreposições e efeitos.

---

# Flexbox

Flexbox organiza elementos **em uma direção** (linha ou coluna).

---

## Container flex

```css
.container {
  display: flex;          /* ativa flexbox */
  flex-direction: row;    /* direção: linha (padrão) ou column */
  justify-content: space-between; /* alinhamento horizontal */
  align-items: center;    /* alinhamento vertical */
  gap: 16px;              /* espaçamento entre itens */
}
```

- `justify-content` controla distribuição ao longo do eixo principal.
    
- `align-items` controla alinhamento no eixo transversal.
    

---

## Itens flex

```css
.item {
  flex: 1; /* cada item ocupa a mesma proporção do espaço restante */
}
.item-2 {
  flex: 2; /* este item será duas vezes maior que os com flex:1 */
}
```

---

# Grid Layout

Grid organiza elementos **em duas dimensões: linhas e colunas**.

```css
.grid {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr; /* três colunas de tamanhos iguais */
  gap: 20px;
}
```

**1fr** significa **uma fração do espaço disponível**. É como uma "fatia" do bolo.

Você pode misturar frações com tamanhos fixos:

```css
grid-template-columns: 200px 1fr 2fr;
/* primeira coluna 200px, segunda 1 parte, terceira 2 partes */
```

**Grid avançado (para depois):** `grid-template-rows`, `grid-area`, `repeat()`, `minmax()`.

**O que você percebe?**  
Grid é poderoso para layouts completos, enquanto Flexbox é ótimo para componentes unidimensionais.

---

# Ferramentas do Navegador (DevTools)

Todo navegador moderno tem ferramentas para desenvolvedor. Para abrir:

- Chrome/Edge: `F12` ou botão direito > Inspecionar
    
- Firefox: `F12` ou botão direito > Inspecionar elemento
    

**O que você pode fazer:**

- Ver o HTML e CSS de qualquer elemento.
    
- Modificar estilos temporariamente (ótimo para testar).
    
- Visualizar o box model (dimensões, padding, margin).
    
- Ver quais regras estão sendo aplicadas e qual a especificidade.
    
- Simular dispositivos móveis.
    

**Exercício:** Abra o DevTools na sua página, selecione o título e altere a cor ali mesmo. Depois desative uma regra e veja o efeito.

---

# Variáveis CSS (Custom Properties)

Variáveis permitem armazenar valores e reutilizá-los.

```css
:root {
  --cor-principal: #3498db;
  --espacamento: 16px;
}
h1 {
  color: var(--cor-principal);
  margin-bottom: var(--espacamento);
}
```

**Vantagens:**

- Facilita manutenção (mude um valor, muda em todo lugar).
    
- Podem ser alteradas com JavaScript ou media queries (temas).
    

---

# Responsividade (Media Queries)

Permitem adaptar a página a diferentes telas.

```css
/* Estilos padrão (mobile first) */
.container {
  flex-direction: column;
}
/* Telas maiores que 768px */
@media (min-width: 768px) {
  .container {
    flex-direction: row;
  }
}
```

**O que você percebe?**  
O layout se reorganiza conforme o tamanho da tela.

---

# Acessibilidade no CSS

Algumas práticas simples:

- Use contraste suficiente entre texto e fundo (verifique com ferramentas).
    
- Não dependa apenas de cor para passar informação (ex.: use também ícones ou sublinhado em links).
    
- Garanta que elementos focáveis tenham um indicador visível (`:focus`).
    
- Use unidades relativas (`rem`) para texto, permitindo que usuários aumentem a fonte.
    

```css
a:focus {
  outline: 2px solid #007bff;
}
```

---

# 50 Exercícios práticos

Faça cada exercício no seu **index.html + style.css**.

Observe sempre o resultado.

**Primeiros exercícios resolvidos (exemplo):**

1. **Pinte `h1` de vermelho**
    
```    css    
    h1 { color: red; }
```
    
2. **Aumente `font-size` de `p` para 18px**
    
```    css    
    p { font-size: 18px; }
```
    
3. **Mude o fundo da página para cinza claro**
    
    ```css
    
    body { background-color: #f0f0f0; }
    ```
    
4. **Adicione `padding: 20px` ao `body`**
    
```    css
       body { padding: 20px; }
```
    
5. **Ative `box-sizing: border-box` globalmente**
    
```    css
    * { box-sizing: border-box; }
```
    

Continue com os demais:

6. Crie uma classe `.card` com borda sólida, padding e margin.
    
7. Centralize o `h1` com `text-align: center`.
    
8. Transforme o texto do `h2` em maiúsculas.
    
9. Ajuste `line-height` dos parágrafos para 1.6.
    
10. Troque a fonte do site para 'Open Sans' (Google Fonts).
    

11–20: Botões com hover, links sem sublinhado, overlay semitransparente, cabeçalho fixo, menu horizontal com flexbox, cartões lado a lado, sombras, bordas arredondadas, listas customizadas, sticky menu.

21–30: Formulário estilizado, pseudo-elementos `::before`, uso de `rem` para espaçamento, transição de cor no hover, animação simples de fade, grid de 2 colunas, galeria de imagens responsiva, tabela com zebrado, modal básico, badge de notificação.

31–40: Variáveis CSS para cores, uso de `calc()` para larguras, `clamp()` para fontes, footer sempre no fundo, layout de página completa com grid, seção hero com gradiente, cards com altura igual, imagem redonda com `border-radius`, ícones com `::before`, menu mobile com media query.

41–50: Página de contato com campos, validação visual com `:invalid`, loading spinner com animação, tooltip com pseudo-elementos, acordeon simples, abas com radio buttons, carrossel básico, página de perfil, dashboard simples, site completo integrando tudo.

---

###### Projeto final

Agora vamos construir uma página simples que consolida tudo. Use o HTML abaixo como base e crie o CSS no arquivo `style.css`.

```html

<!DOCTYPE html>
<html>
<head>
  <title>Meu Site</title>
  <link rel="stylesheet" href="style.css">
  <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap" rel="stylesheet">
</head>
<body>
  <header class="header">
    <div class="logo">MeuSite</div>
    <nav class="menu">
      <ul>
        <li><a href="#">Início</a></li>
        <li><a href="#">Sobre</a></li>
        <li><a href="#">Serviços</a></li>
        <li><a href="#">Contato</a></li>
      </ul>
    </nav>
  </header>
  <section class="hero">
    <h1>Bem-vindo ao MeuSite</h1>
    <p>Uma página simples para praticar CSS.</p>
  </section>
  <section class="cards">
    <div class="card">
      <h3>Card 1</h3>
      <p>Conteúdo do primeiro card.</p>
    </div>
    <div class="card">
      <h3>Card 2</h3>
      <p>Conteúdo do segundo card.</p>
    </div>
    <div class="card">
      <h3>Card 3</h3>
      <p>Conteúdo do terceiro card.</p>
    </div>
  </section>
  <footer class="footer">
    <p>&copy; 2025 MeuSite. Todos os direitos reservados.</p>
  </footer>
</body>
</html>
```

**Desafio:** Estilize a página com:

- Cabeçalho fixo ou com padding.
    
- Menu horizontal com flexbox.
    
- Hero com gradiente de fundo e texto centralizado.
    
- Cards lado a lado usando grid (3 colunas em desktop, 1 em mobile).
    
- Rodapé simples com cor de fundo.
    
- Use variáveis CSS para cores principais.
    
- Adicione uma media query para telas pequenas (max-width: 768px) que empilhe os cards.
    

**Dica:** Comece pelo reset básico (`* { box-sizing: border-box; margin:0; padding:0; }`). Depois vá estilizando cada seção.

---

# Próximos passos

Parabéns! Você já tem uma base sólida. Agora pode explorar:

- **Flexbox avançado** (propriedades como `align-self`, `order`).
    
- **Grid avançado** (`grid-template-areas`, `minmax`, `auto-fit`).
    
- **Animações CSS** (`@keyframes`, `transition`, `animation`).
    
- **Arquitetura CSS** (BEM, SMACSS) para organizar projetos grandes.
    
- **Frameworks** (Tailwind, Bootstrap) para acelerar o desenvolvimento.
    
- **Pré-processadores** (Sass) para escrever CSS mais poderoso.
    

Continue praticando e construindo pequenos projetos. O segredo é a constância.

---

**Observação final:** Este guia é um ponto de partida. A web está sempre evoluindo, e o CSS também. Mantenha-se curioso e nunca pare de experimentar.

Bons estudos! 🚀
