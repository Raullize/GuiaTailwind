<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=06B6D4&height=120&section=header&fontSize=30&fontColor=fff&animation=twinkling&fontAlignY=35"/>

# Flexbox com Tailwind CSS

O Flexbox é um modelo de layout do CSS que permite criar designs flexíveis e responsivos. O Tailwind CSS oferece uma série de classes utilitárias que facilitam o uso do Flexbox sem precisar escrever CSS personalizado.

## Habilitando o Flexbox

Para usar o Flexbox, primeiro defina um elemento como um container flex:

```html
<div class="flex">
  <!-- Itens flex aqui -->
</div>

<!-- Para display: inline-flex -->
<div class="inline-flex">
  <!-- Itens flex aqui -->
</div>
```

## Direção do Flex

Controle a direção dos itens dentro do container flex:

```html
<!-- Horizontal (padrão) -->
<div class="flex flex-row">
  <div>Item 1</div>
  <div>Item 2</div>
  <div>Item 3</div>
</div>

<!-- Horizontal reverso -->
<div class="flex flex-row-reverse">
  <div>Item 1</div>
  <div>Item 2</div>
  <div>Item 3</div>
</div>

<!-- Vertical -->
<div class="flex flex-col">
  <div>Item 1</div>
  <div>Item 2</div>
  <div>Item 3</div>
</div>

<!-- Vertical reverso -->
<div class="flex flex-col-reverse">
  <div>Item 1</div>
  <div>Item 2</div>
  <div>Item 3</div>
</div>
```

## Quebra de Linha (Wrap)

Defina se os itens devem quebrar para a próxima linha quando não couberem no container:

```html
<!-- Sem quebra (padrão) -->
<div class="flex flex-nowrap">
  <!-- Itens aqui -->
</div>

<!-- Com quebra -->
<div class="flex flex-wrap">
  <!-- Itens aqui -->
</div>

<!-- Quebra reversa -->
<div class="flex flex-wrap-reverse">
  <!-- Itens aqui -->
</div>
```

## ↔️ Alinhamento Horizontal (Justify Content)

Controle como os itens são distribuídos horizontalmente (no eixo principal):

```html
<!-- Alinhado ao início (padrão) -->
<div class="flex justify-start">
  <div>Item 1</div>
  <div>Item 2</div>
  <div>Item 3</div>
</div>

<!-- Alinhado ao final -->
<div class="flex justify-end">
  <div>Item 1</div>
  <div>Item 2</div>
  <div>Item 3</div>
</div>

<!-- Centralizado -->
<div class="flex justify-center">
  <div>Item 1</div>
  <div>Item 2</div>
  <div>Item 3</div>
</div>

<!-- Espaço entre os itens -->
<div class="flex justify-between">
  <div>Item 1</div>
  <div>Item 2</div>
  <div>Item 3</div>
</div>

<!-- Espaço ao redor dos itens -->
<div class="flex justify-around">
  <div>Item 1</div>
  <div>Item 2</div>
  <div>Item 3</div>
</div>

<!-- Espaço uniforme entre e ao redor dos itens -->
<div class="flex justify-evenly">
  <div>Item 1</div>
  <div>Item 2</div>
  <div>Item 3</div>
</div>
```

## ↕️ Alinhamento Vertical (Align Items)

Controle como os itens são alinhados verticalmente (no eixo transversal):

```html
<!-- Esticados (padrão) -->
<div class="flex items-stretch h-24">
  <div>Item 1</div>
  <div>Item 2</div>
  <div>Item 3</div>
</div>

<!-- Alinhados ao início -->
<div class="flex items-start h-24">
  <div>Item 1</div>
  <div>Item 2</div>
  <div>Item 3</div>
</div>

<!-- Alinhados ao final -->
<div class="flex items-end h-24">
  <div>Item 1</div>
  <div>Item 2</div>
  <div>Item 3</div>
</div>

<!-- Centralizados -->
<div class="flex items-center h-24">
  <div>Item 1</div>
  <div>Item 2</div>
  <div>Item 3</div>
</div>

<!-- Alinhados pela linha de base do texto -->
<div class="flex items-baseline h-24">
  <div class="text-sm">Item 1</div>
  <div class="text-lg">Item 2</div>
  <div class="text-xl">Item 3</div>
</div>
```

## Alinhamento de Linhas Múltiplas (Align Content)

Quando há múltiplas linhas (flex-wrap), controle como essas linhas são distribuídas:

```html
<!-- Alinhadas ao início -->
<div class="flex flex-wrap content-start h-48">
  <!-- Múltiplos itens que quebram linha -->
</div>

<!-- Alinhadas ao final -->
<div class="flex flex-wrap content-end h-48">
  <!-- Itens aqui -->
</div>

<!-- Centralizadas -->
<div class="flex flex-wrap content-center h-48">
  <!-- Itens aqui -->
</div>

<!-- Espaço entre as linhas -->
<div class="flex flex-wrap content-between h-48">
  <!-- Itens aqui -->
</div>

<!-- Espaço ao redor das linhas -->
<div class="flex flex-wrap content-around h-48">
  <!-- Itens aqui -->
</div>

<!-- Esticadas (padrão) -->
<div class="flex flex-wrap content-stretch h-48">
  <!-- Itens aqui -->
</div>
```

## Alinhamento Individual (Self)

Você pode sobrescrever o alinhamento de itens específicos:

```html
<div class="flex items-start h-24">
  <div>Início (padrão)</div>
  <div class="self-center">Centralizado</div>
  <div class="self-end">Final</div>
  <div class="self-stretch">Esticado</div>
  <div class="self-auto">Auto</div>
</div>
```

## Controle de Crescimento/Encolhimento (Flex)

### Flex Grow (Crescimento)

Controla quanto um item pode crescer em relação aos outros:

```html
<div class="flex">
  <div class="flex-grow-0">Não cresce</div>
  <div class="flex-grow">Cresce</div>
  <div class="flex-grow-0">Não cresce</div>
</div>

<!-- Valores numéricos -->
<div class="flex">
  <div class="flex-grow">Cresce 1</div>
  <div class="grow-[2]">Cresce 2x mais</div>
  <div class="grow-[3]">Cresce 3x mais</div>
</div>
```

### Flex Shrink (Encolhimento)

Controla quanto um item pode encolher em relação aos outros:

```html
<div class="flex">
  <div class="flex-shrink">Encolhe (padrão)</div>
  <div class="flex-shrink-0">Não encolhe</div>
  <div class="flex-shrink">Encolhe (padrão)</div>
</div>

<!-- Valores numéricos -->
<div class="flex">
  <div class="shrink-[1]">Encolhe normal</div>
  <div class="shrink-[2]">Encolhe 2x mais</div>
  <div class="shrink-[3]">Encolhe 3x mais</div>
</div>
```

### Flex Basis (Tamanho Base)

Define o tamanho inicial de um item antes de crescer ou encolher:

```html
<div class="flex">
  <div class="basis-1/4">25%</div>
  <div class="basis-1/2">50%</div>
  <div class="basis-1/4">25%</div>
</div>

<div class="flex">
  <div class="basis-auto">Auto</div>
  <div class="basis-0">0</div>
  <div class="basis-96">24rem</div>
</div>
```

### Atalhos Flex

```html
<!-- flex-1: flex-grow: 1, flex-shrink: 1, flex-basis: 0% -->
<div class="flex-1">Cresce e encolhe igualmente, começando de 0</div>

<!-- flex-auto: flex-grow: 1, flex-shrink: 1, flex-basis: auto -->
<div class="flex-auto">Cresce e encolhe igualmente, respeitando as dimensões iniciais</div>

<!-- flex-initial: flex-grow: 0, flex-shrink: 1, flex-basis: auto -->
<div class="flex-initial">Não cresce, mas encolhe se necessário</div>

<!-- flex-none: flex-grow: 0, flex-shrink: 0, flex-basis: auto -->
<div class="flex-none">Não cresce nem encolhe</div>
```

## Ordem

Controle a ordem dos itens independentemente da ordem no HTML:

```html
<div class="flex">
  <div class="order-3">3º visual, 1º no HTML</div>
  <div class="order-1">1º visual, 2º no HTML</div>
  <div class="order-2">2º visual, 3º no HTML</div>
</div>

<!-- Ordem específica -->
<div class="flex">
  <div class="order-[5]">5</div>
  <div class="order-[1]">1</div>
  <div class="order-[9]">9</div>
</div>

<!-- Ordem negativa vem antes dos positivos -->
<div class="flex">
  <div class="order-2">2</div>
  <div class="order-1">1</div>
  <div class="order-[-1]">Primeiro</div>
</div>
```

## Flexbox Responsivo

Adapte o layout flexbox para diferentes tamanhos de tela:

```html
<!-- Coluna em telas pequenas, linha em médias -->
<div class="flex flex-col md:flex-row">
  <div>Item 1</div>
  <div>Item 2</div>
  <div>Item 3</div>
</div>

<!-- Centralização responsiva -->
<div class="flex justify-start md:justify-center lg:justify-end">
  <div>Item 1</div>
  <div>Item 2</div>
  <div>Item 3</div>
</div>

<!-- Comportamento de crescimento responsivo -->
<div class="flex">
  <div class="flex-grow-0 md:flex-grow">Cresce a partir de telas médias</div>
  <div class="flex-grow md:flex-grow-0">Para de crescer em telas médias</div>
</div>
```

## Espaçamento entre Itens (Gap)

O Tailwind oferece classes para controlar o espaço entre itens sem usar margens:

```html
<!-- Espaço igual horizontal e vertical -->
<div class="flex flex-wrap gap-4">
  <div>Item 1</div>
  <div>Item 2</div>
  <div>Item 3</div>
</div>

<!-- Espaço horizontal (coluna) -->
<div class="flex flex-wrap gap-x-4">
  <div>Item 1</div>
  <div>Item 2</div>
  <div>Item 3</div>
</div>

<!-- Espaço vertical (linha) -->
<div class="flex flex-wrap gap-y-8">
  <div>Item 1</div>
  <div>Item 2</div>
  <div>Item 3</div>
</div>

<!-- Gap responsivo -->
<div class="flex gap-2 md:gap-4 lg:gap-6">
  <div>Item 1</div>
  <div>Item 2</div>
  <div>Item 3</div>
</div>
```

## Exemplos Práticos

### 1. Barra de Navegação Responsiva

```html
<nav class="flex flex-col sm:flex-row justify-between items-center bg-white p-4">
  <div class="flex items-center">
    <img src="logo.svg" alt="Logo" class="h-8 w-auto">
    <span class="ml-2 text-xl font-bold">Minha Marca</span>
  </div>
  
  <div class="flex flex-col sm:flex-row sm:space-x-4 mt-4 sm:mt-0">
    <a href="#" class="px-2 py-1 text-blue-600 font-medium">Home</a>
    <a href="#" class="px-2 py-1 text-gray-600 hover:text-blue-600">Produtos</a>
    <a href="#" class="px-2 py-1 text-gray-600 hover:text-blue-600">Sobre</a>
    <a href="#" class="px-2 py-1 text-gray-600 hover:text-blue-600">Contato</a>
  </div>
</nav>
```

### 2. Card com Layout Flexível

```html
<div class="flex flex-col sm:flex-row bg-white shadow-md rounded-lg overflow-hidden">
  <img src="image.jpg" alt="Imagem" class="sm:w-48 h-48 sm:h-auto object-cover">
  
  <div class="p-6 flex flex-col flex-grow">
    <h3 class="text-xl font-semibold text-gray-800">Título do Card</h3>
    <p class="mt-2 text-gray-600 flex-grow">Descrição do card que pode ocupar várias linhas dependendo do conteúdo.</p>
    
    <div class="mt-4 flex justify-between items-center">
      <span class="text-blue-600 font-medium">$49.99</span>
      <button class="px-4 py-2 bg-blue-600 text-white rounded-lg hover:bg-blue-700">Comprar</button>
    </div>
  </div>
</div>
```

### 3. Layout de Página com Sidebar

```html
<div class="flex flex-col md:flex-row min-h-screen">
  <!-- Sidebar -->
  <aside class="w-full md:w-64 bg-gray-800 md:min-h-screen p-4">
    <div class="text-white font-bold mb-6">Painel Admin</div>
    
    <nav class="flex flex-col space-y-2">
      <a href="#" class="px-4 py-2 text-white bg-gray-700 rounded">Dashboard</a>
      <a href="#" class="px-4 py-2 text-gray-300 hover:bg-gray-700 rounded">Usuários</a>
      <a href="#" class="px-4 py-2 text-gray-300 hover:bg-gray-700 rounded">Produtos</a>
      <a href="#" class="px-4 py-2 text-gray-300 hover:bg-gray-700 rounded">Relatórios</a>
      <a href="#" class="px-4 py-2 text-gray-300 hover:bg-gray-700 rounded">Configurações</a>
    </nav>
  </aside>
  
  <!-- Conteúdo principal -->
  <main class="flex-grow p-6">
    <h1 class="text-2xl font-bold mb-6">Dashboard</h1>
    
    <!-- Cards de estatísticas -->
    <div class="flex flex-wrap gap-4">
      <div class="flex-grow flex items-center p-4 bg-white shadow rounded-lg">
        <div class="bg-blue-500 p-3 rounded-full">
          <!-- Ícone aqui -->
        </div>
        <div class="ml-4">
          <h2 class="text-gray-500">Usuários</h2>
          <div class="text-2xl font-semibold">1,284</div>
        </div>
      </div>
      
      <div class="flex-grow flex items-center p-4 bg-white shadow rounded-lg">
        <div class="bg-green-500 p-3 rounded-full">
          <!-- Ícone aqui -->
        </div>
        <div class="ml-4">
          <h2 class="text-gray-500">Receita</h2>
          <div class="text-2xl font-semibold">$12,458</div>
        </div>
      </div>
      
      <div class="flex-grow flex items-center p-4 bg-white shadow rounded-lg">
        <div class="bg-orange-500 p-3 rounded-full">
          <!-- Ícone aqui -->
        </div>
        <div class="ml-4">
          <h2 class="text-gray-500">Pedidos</h2>
          <div class="text-2xl font-semibold">64</div>
        </div>
      </div>
    </div>
  </main>
</div>
```

### 4. Layout de Hero com Centralização

```html
<div class="flex items-center justify-center min-h-screen bg-gradient-to-r from-blue-500 to-indigo-600 p-6">
  <div class="flex flex-col items-center text-center max-w-2xl">
    <h1 class="text-4xl md:text-6xl font-bold text-white leading-tight">
      Crie designs incríveis com Flexbox e Tailwind
</h1>
    <p class="mt-6 text-xl text-blue-100">
      Controle total do layout com classes Flexbox intuitivas e responsivas.
    </p>
    <div class="mt-10 flex flex-col sm:flex-row gap-4">
      <a href="#" class="px-8 py-3 bg-white text-indigo-600 font-medium rounded-lg hover:bg-gray-100">
        Comece Agora
      </a>
      <a href="#" class="px-8 py-3 border-2 border-white text-white font-medium rounded-lg hover:bg-white/10">
        Saiba Mais
      </a>
    </div>
  </div>
</div>
```

## Flexbox vs. Grid

O Flexbox é ideal para:
- Layouts unidimensionais (linha OU coluna)
- Distribuir espaço entre itens em uma única dimensão
- Alinhar itens dentro de um container
- Layouts onde o tamanho exato dos itens não é conhecido

O Grid é melhor para:
- Layouts bidimensionais (linhas E colunas simultâneas)
- Posicionamento preciso de itens em uma grade
- Layouts complexos com áreas nomeadas
- Quando você precisa de controle sobre ambas as dimensões

## Links Úteis

- [Documentação de Flexbox no Tailwind](https://tailwindcss.com/docs/flex-direction)
- [Guia de Flexbox da CSS-Tricks](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
- [Flexbox Froggy](https://flexboxfroggy.com/) - Um jogo para aprender Flexbox
- [Can I Use - Flexbox](https://caniuse.com/?search=flexbox) - Compatibilidade com navegadores

---

[⬅️ Voltar para o início](../README.md)

<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=06B6D4&height=120&section=footer"/>