<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=06B6D4&height=120&section=header&fontSize=30&fontColor=fff&animation=twinkling&fontAlignY=35"/>

# 📐 Layout e Espaçamento no Tailwind CSS 📏

O controle preciso do layout e do espaçamento é essencial para criar interfaces harmoniosas. O Tailwind CSS oferece um conjunto abrangente de utilitários para gerenciar espaço, posicionamento e layout de forma eficiente.

## 📏 Sistema de Espaçamento

O Tailwind usa uma escala de espaçamento consistente para padding, margin, width, height e outros utilitários relacionados ao espaço.

### Escala Padrão

- `0` = 0px
- `px` = 1px
- `0.5` = 0.125rem (2px)
- `1` = 0.25rem (4px)
- `1.5` = 0.375rem (6px)
- `2` = 0.5rem (8px)
- `2.5` = 0.625rem (10px)
- `3` = 0.75rem (12px)
- `3.5` = 0.875rem (14px)
- `4` = 1rem (16px)
- `5` = 1.25rem (20px)
- `6` = 1.5rem (24px)
- `7` = 1.75rem (28px)
- `8` = 2rem (32px)
- `9` = 2.25rem (36px)
- `10` = 2.5rem (40px)
- `11` = 2.75rem (44px)
- `12` = 3rem (48px)
- `14` = 3.5rem (56px)
- `16` = 4rem (64px)
- `20` = 5rem (80px)
- `24` = 6rem (96px)
- `28` = 7rem (112px)
- `32` = 8rem (128px)
- `36` = 9rem (144px)
- `40` = 10rem (160px)
- `44` = 11rem (176px)
- `48` = 12rem (192px)
- `52` = 13rem (208px)
- `56` = 14rem (224px)
- `60` = 15rem (240px)
- `64` = 16rem (256px)
- `72` = 18rem (288px)
- `80` = 20rem (320px)
- `96` = 24rem (384px)

## 🔄 Margin (margem)

### Aplicando margens

```html
<!-- Todos os lados -->
<div class="m-4">Margem 1rem em todos os lados</div>

<!-- Horizontal (esquerda e direita) -->
<div class="mx-4">Margem horizontal de 1rem</div>

<!-- Vertical (superior e inferior) -->
<div class="my-4">Margem vertical de 1rem</div>

<!-- Individual -->
<div class="mt-4">Margem superior de 1rem</div>
<div class="mr-4">Margem direita de 1rem</div>
<div class="mb-4">Margem inferior de 1rem</div>
<div class="ml-4">Margem esquerda de 1rem</div>

<!-- Valores negativos -->
<div class="m-4 -ml-2">Margem esquerda negativa de 0.5rem</div>

<!-- Centralização automática -->
<div class="mx-auto w-1/2">Centralizado horizontalmente</div>
```

### Espaçamento entre elementos filhos

O Tailwind oferece o utilitário `space-` para adicionar espaçamento entre elementos filhos:

```html
<!-- Espaço vertical entre os elementos -->
<div class="space-y-4">
  <div>Item 1</div>
  <div>Item 2</div>
  <div>Item 3</div>
</div>

<!-- Espaço horizontal entre os elementos -->
<div class="flex space-x-4">
  <div>Item 1</div>
  <div>Item 2</div>
  <div>Item 3</div>
</div>

<!-- Reverter direção do espaço -->
<div class="flex flex-row-reverse space-x-4 space-x-reverse">
  <div>Item 1</div>
  <div>Item 2</div>
  <div>Item 3</div>
</div>
```

## 🔲 Padding (preenchimento)

### Aplicando padding

```html
<!-- Todos os lados -->
<div class="p-4">Padding 1rem em todos os lados</div>

<!-- Horizontal (esquerda e direita) -->
<div class="px-4">Padding horizontal de 1rem</div>

<!-- Vertical (superior e inferior) -->
<div class="py-4">Padding vertical de 1rem</div>

<!-- Individual -->
<div class="pt-4">Padding superior de 1rem</div>
<div class="pr-4">Padding direito de 1rem</div>
<div class="pb-4">Padding inferior de 1rem</div>
<div class="pl-4">Padding esquerdo de 1rem</div>
```

## 📏 Largura (Width)

O Tailwind fornece utilitários para definir larguras fixas, responsivas e proporcionais.

### Larguras Fixas

```html
<div class="w-0">0px</div>
<div class="w-px">1px</div>
<div class="w-0.5">0.125rem (2px)</div>
<div class="w-1">0.25rem (4px)</div>
<!-- Continua conforme a escala de espaçamento -->
<div class="w-96">24rem (384px)</div>
```

### Larguras Proporcionais

```html
<div class="w-1/2">50%</div>
<div class="w-1/3">33.333333%</div>
<div class="w-2/3">66.666667%</div>
<div class="w-1/4">25%</div>
<div class="w-2/4">50%</div>
<div class="w-3/4">75%</div>
<div class="w-1/5">20%</div>
<!-- etc. -->
<div class="w-full">100%</div>
```

### Larguras Especiais

```html
<div class="w-auto">Auto</div>
<div class="w-screen">100vw (largura da viewport)</div>
<div class="w-min">min-content</div>
<div class="w-max">max-content</div>
<div class="w-fit">fit-content</div>
```

### Larguras Máximas e Mínimas

```html
<div class="min-w-0">min-width: 0px</div>
<div class="min-w-full">min-width: 100%</div>
<div class="min-w-min">min-width: min-content</div>
<div class="min-w-max">min-width: max-content</div>

<div class="max-w-none">max-width: none</div>
<div class="max-w-xs">max-width: 20rem (320px)</div>
<div class="max-w-sm">max-width: 24rem (384px)</div>
<div class="max-w-md">max-width: 28rem (448px)</div>
<div class="max-w-lg">max-width: 32rem (512px)</div>
<div class="max-w-xl">max-width: 36rem (576px)</div>
<div class="max-w-2xl">max-width: 42rem (672px)</div>
<div class="max-w-3xl">max-width: 48rem (768px)</div>
<div class="max-w-4xl">max-width: 56rem (896px)</div>
<div class="max-w-5xl">max-width: 64rem (1024px)</div>
<div class="max-w-6xl">max-width: 72rem (1152px)</div>
<div class="max-w-7xl">max-width: 80rem (1280px)</div>
<div class="max-w-full">max-width: 100%</div>
<div class="max-w-screen-sm">max-width: 640px</div>
<div class="max-w-screen-md">max-width: 768px</div>
<div class="max-w-screen-lg">max-width: 1024px</div>
<div class="max-w-screen-xl">max-width: 1280px</div>
<div class="max-w-screen-2xl">max-width: 1536px</div>
```

## 📐 Altura (Height)

Assim como ocorre com larguras, o Tailwind oferece diversas classes para controlar alturas.

### Alturas Fixas

```html
<div class="h-0">0px</div>
<div class="h-px">1px</div>
<div class="h-0.5">0.125rem (2px)</div>
<!-- Continua conforme a escala de espaçamento -->
<div class="h-96">24rem (384px)</div>
```

### Alturas Proporcionais

```html
<div class="h-1/2">50%</div>
<div class="h-1/3">33.333333%</div>
<div class="h-2/3">66.666667%</div>
<div class="h-1/4">25%</div>
<div class="h-2/4">50%</div>
<div class="h-3/4">75%</div>
<div class="h-1/5">20%</div>
<!-- etc. -->
<div class="h-full">100%</div>
```

### Alturas Especiais

```html
<div class="h-auto">Auto</div>
<div class="h-screen">100vh (altura da viewport)</div>
<div class="h-min">min-content</div>
<div class="h-max">max-content</div>
<div class="h-fit">fit-content</div>
```

### Alturas Máximas e Mínimas

```html
<div class="min-h-0">min-height: 0px</div>
<div class="min-h-full">min-height: 100%</div>
<div class="min-h-screen">min-height: 100vh</div>
<div class="min-h-min">min-height: min-content</div>
<div class="min-h-max">min-height: max-content</div>

<div class="max-h-none">max-height: none</div>
<div class="max-h-0">max-height: 0px</div>
<div class="max-h-px">max-height: 1px</div>
<!-- Continua conforme a escala de espaçamento -->
<div class="max-h-full">max-height: 100%</div>
<div class="max-h-screen">max-height: 100vh</div>
```

## 🧮 Dimensionamento de Linhas e Colunas no Grid

### Grid Template Columns

```html
<div class="grid grid-cols-1">1 coluna</div>
<div class="grid grid-cols-2">2 colunas</div>
<div class="grid grid-cols-3">3 colunas</div>
<div class="grid grid-cols-4">4 colunas</div>
<div class="grid grid-cols-5">5 colunas</div>
<div class="grid grid-cols-6">6 colunas</div>
<div class="grid grid-cols-7">7 colunas</div>
<div class="grid grid-cols-8">8 colunas</div>
<div class="grid grid-cols-9">9 colunas</div>
<div class="grid grid-cols-10">10 colunas</div>
<div class="grid grid-cols-11">11 colunas</div>
<div class="grid grid-cols-12">12 colunas</div>
<div class="grid grid-cols-none">No columns</div>
```

### Grid Template Rows

```html
<div class="grid grid-rows-1">1 linha</div>
<div class="grid grid-rows-2">2 linhas</div>
<div class="grid grid-rows-3">3 linhas</div>
<div class="grid grid-rows-4">4 linhas</div>
<div class="grid grid-rows-5">5 linhas</div>
<div class="grid grid-rows-6">6 linhas</div>
<div class="grid grid-rows-none">No explicit rows</div>
```

## 📍 Posicionamento

### Position

```html
<div class="static">Posicionamento estático (padrão)</div>
<div class="relative">Posicionamento relativo</div>
<div class="absolute">Posicionamento absoluto</div>
<div class="fixed">Posicionamento fixo</div>
<div class="sticky">Posicionamento sticky</div>
```

### Coordenadas

```html
<div class="top-0">top: 0px</div>
<div class="right-0">right: 0px</div>
<div class="bottom-0">bottom: 0px</div>
<div class="left-0">left: 0px</div>

<div class="top-auto">top: auto</div>
<div class="right-auto">right: auto</div>
<div class="bottom-auto">bottom: auto</div>
<div class="left-auto">left: auto</div>

<!-- Seguindo a escala de espaçamento -->
<div class="top-1">top: 0.25rem</div>
<div class="right-4">right: 1rem</div>
<div class="bottom-8">bottom: 2rem</div>
<div class="left-12">left: 3rem</div>

<!-- Valores negativos -->
<div class="-top-1">top: -0.25rem</div>
<div class="-right-4">right: -1rem</div>
```

### Exemplos de Posicionamento

```html
<!-- Elemento absoluto no canto superior direito -->
<div class="relative">
  <div class="absolute top-0 right-0">
    Canto superior direito
  </div>
</div>

<!-- Elemento centralizado absolutamente -->
<div class="relative">
  <div class="absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2">
    Centralizado
  </div>
</div>

<!-- Elemento fixo na parte inferior da tela -->
<div class="fixed bottom-0 left-0 right-0">
  Barra fixa no rodapé
</div>

<!-- Menu sticky que adere ao topo durante a rolagem -->
<div class="sticky top-0">
  Menu que permanece visível
</div>
```

## 🌟 Z-Index

O z-index controla o empilhamento de elementos posicionados (não estáticos).

```html
<div class="z-0">z-index: 0</div>
<div class="z-10">z-index: 10</div>
<div class="z-20">z-index: 20</div>
<div class="z-30">z-index: 30</div>
<div class="z-40">z-index: 40</div>
<div class="z-50">z-index: 50</div>
<div class="z-auto">z-index: auto</div>

<!-- Valores negativos -->
<div class="-z-10">z-index: -10</div>
<div class="-z-20">z-index: -20</div>
```

## 📊 Display

A propriedade display controla como um elemento é tratado no fluxo do documento.

```html
<div class="block">display: block</div>
<div class="inline-block">display: inline-block</div>
<div class="inline">display: inline</div>
<div class="flex">display: flex</div>
<div class="inline-flex">display: inline-flex</div>
<div class="table">display: table</div>
<div class="inline-table">display: inline-table</div>
<div class="table-caption">display: table-caption</div>
<div class="table-cell">display: table-cell</div>
<div class="table-column">display: table-column</div>
<div class="table-column-group">display: table-column-group</div>
<div class="table-footer-group">display: table-footer-group</div>
<div class="table-header-group">display: table-header-group</div>
<div class="table-row-group">display: table-row-group</div>
<div class="table-row">display: table-row</div>
<div class="flow-root">display: flow-root</div>
<div class="grid">display: grid</div>
<div class="inline-grid">display: inline-grid</div>
<div class="contents">display: contents</div>
<div class="list-item">display: list-item</div>
<div class="hidden">display: none</div>
```

## 🧩 Overflow

Os utilitários de overflow controlam como o conteúdo é exibido quando ultrapassa os limites do seu container.

```html
<div class="overflow-auto">Barra de rolagem quando necessário</div>
<div class="overflow-hidden">Esconde o conteúdo excedente</div>
<div class="overflow-visible">Mostra o conteúdo que transborda</div>
<div class="overflow-scroll">Sempre mostra barras de rolagem</div>

<!-- Controlando apenas eixo X -->
<div class="overflow-x-auto">Rolagem horizontal automática</div>
<div class="overflow-x-hidden">Esconde o conteúdo horizontal excedente</div>
<div class="overflow-x-visible">Mostra o conteúdo horizontal que transborda</div>
<div class="overflow-x-scroll">Sempre mostra barra de rolagem horizontal</div>

<!-- Controlando apenas eixo Y -->
<div class="overflow-y-auto">Rolagem vertical automática</div>
<div class="overflow-y-hidden">Esconde o conteúdo vertical excedente</div>
<div class="overflow-y-visible">Mostra o conteúdo vertical que transborda</div>
<div class="overflow-y-scroll">Sempre mostra barra de rolagem vertical</div>
```

## 🏠 Container

O Tailwind fornece um utilitário `container` para criar containers responsivos com largura máxima:

```html
<div class="container">
  <!-- Conteúdo aqui -->
</div>
```

Por padrão, o `container` tem as seguintes larguras máximas nos breakpoints:

- `xs`: 100%
- `sm`: 640px
- `md`: 768px
- `lg`: 1024px
- `xl`: 1280px
- `2xl`: 1536px

Para centralizar o container:

```html
<div class="container mx-auto">
  <!-- Conteúdo centralizado -->
</div>
```

Para adicionar padding horizontal:

```html
<div class="container mx-auto px-4">
  <!-- Conteúdo com padding horizontal -->
</div>
```

## 🎯 Box Sizing

O Tailwind usa `box-sizing: border-box` por padrão, mas você pode alterá-lo:

```html
<div class="box-border">box-sizing: border-box (padrão)</div>
<div class="box-content">box-sizing: content-box</div>
```

## 📱 Object Fit

Controla como uma imagem ou vídeo é redimensionado para caber em seu container:

```html
<img class="object-contain" src="...">
<img class="object-cover" src="...">
<img class="object-fill" src="...">
<img class="object-none" src="...">
<img class="object-scale-down" src="...">
```

## 🛠️ Exemplos Práticos

### Layout de Card Responsivo

```html
<div class="max-w-md mx-auto bg-white rounded-xl shadow-md overflow-hidden md:max-w-2xl">
  <div class="md:flex">
    <div class="md:shrink-0">
      <img class="h-48 w-full object-cover md:h-full md:w-48" src="..." alt="Imagem">
    </div>
    <div class="p-8">
      <div class="uppercase tracking-wide text-sm text-indigo-500 font-semibold">Categoria</div>
      <a href="#" class="block mt-1 text-lg leading-tight font-medium text-black">
        Título do Card que quebra em duas linhas se necessário
      </a>
      <p class="mt-2 text-slate-500">
        Conteúdo do card com texto descritivo mais longo que ocupa várias linhas.
      </p>
    </div>
  </div>
</div>
```

### Layout de Hero Section

```html
<div class="relative">
  <div class="absolute inset-0">
    <img class="w-full h-full object-cover" src="..." alt="Background">
    <div class="absolute inset-0 bg-gray-900 opacity-75"></div>
  </div>
  <div class="relative max-w-7xl mx-auto px-4 py-24 sm:px-6 sm:py-32 lg:px-8">
    <h1 class="text-4xl font-extrabold tracking-tight text-white sm:text-5xl lg:text-6xl">
      Título Principal
    </h1>
    <p class="mt-6 max-w-3xl text-xl text-gray-300">
      Subtítulo ou descrição que explica melhor o propósito da seção.
    </p>
    <div class="mt-10">
      <a href="#" class="inline-block bg-indigo-600 py-3 px-8 rounded-md text-base font-medium text-white hover:bg-indigo-700">
        Botão de Ação
      </a>
    </div>
  </div>
</div>
```

### Layout de Menu Responsivo

```html
<nav class="bg-white shadow">
  <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
    <div class="flex justify-between h-16">
      <div class="flex">
        <div class="flex-shrink-0 flex items-center">
          <img class="h-8 w-auto" src="logo.svg" alt="Logo">
        </div>
        <div class="hidden sm:ml-6 sm:flex sm:space-x-8">
          <a href="#" class="border-indigo-500 text-gray-900 inline-flex items-center px-1 pt-1 border-b-2 text-sm font-medium">
            Home
          </a>
          <a href="#" class="border-transparent text-gray-500 hover:border-gray-300 hover:text-gray-700 inline-flex items-center px-1 pt-1 border-b-2 text-sm font-medium">
            Sobre
          </a>
          <a href="#" class="border-transparent text-gray-500 hover:border-gray-300 hover:text-gray-700 inline-flex items-center px-1 pt-1 border-b-2 text-sm font-medium">
            Serviços
          </a>
          <a href="#" class="border-transparent text-gray-500 hover:border-gray-300 hover:text-gray-700 inline-flex items-center px-1 pt-1 border-b-2 text-sm font-medium">
            Contato
          </a>
        </div>
      </div>
      <div class="-mr-2 flex items-center sm:hidden">
        <button type="button" class="inline-flex items-center justify-center p-2 rounded-md text-gray-400 hover:text-gray-500 hover:bg-gray-100 focus:outline-none focus:ring-2 focus:ring-inset focus:ring-indigo-500">
          <span class="sr-only">Abrir menu</span>
          <!-- Ícone de menu -->
        </button>
      </div>
    </div>
  </div>
</nav>
```

## 🔗 Links Úteis

- [Documentação de espaçamento](https://tailwindcss.com/docs/padding)
- [Documentação de layout](https://tailwindcss.com/docs/container)
- [Utilitários de posicionamento](https://tailwindcss.com/docs/position)
- [Sistema de grid](https://tailwindcss.com/docs/grid-template-columns)

---

[⬅️ Voltar para o início](../README.md)

<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=06B6D4&height=120&section=footer"/> 