<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=06B6D4&height=120&section=header&fontSize=30&fontColor=fff&animation=twinkling&fontAlignY=35"/>

# Utilitários Fundamentais do Tailwind CSS

O Tailwind CSS é construído em torno do conceito de classes utilitárias - pequenas classes de propósito único que você pode combinar para criar qualquer design. Nesta seção, exploraremos os utilitários mais fundamentais que formam a base do framework.

## Espaçamento

O Tailwind oferece classes para controlar margens e preenchimentos (padding) em todos os lados ou em lados específicos.

### Padding (preenchimento interno)

```html
<div class="p-4">Todos os lados</div>
<div class="px-4">Esquerda e direita</div>
<div class="py-4">Topo e base</div>
<div class="pt-4">Apenas topo</div>
<div class="pr-4">Apenas direita</div>
<div class="pb-4">Apenas base</div>
<div class="pl-4">Apenas esquerda</div>
```

### Margin (margem externa)

```html
<div class="m-4">Todos os lados</div>
<div class="mx-4">Esquerda e direita</div>
<div class="my-4">Topo e base</div>
<div class="mt-4">Apenas topo</div>
<div class="mr-4">Apenas direita</div>
<div class="mb-4">Apenas base</div>
<div class="ml-4">Apenas esquerda</div>
<div class="mx-auto">Centralizar horizontalmente</div>
```

### Escala de espaçamento

O Tailwind usa uma escala padrão que pode ser personalizada:

- `0` = 0px
- `0.5` = 0.125rem (2px)
- `1` = 0.25rem (4px)
- `2` = 0.5rem (8px)
- `3` = 0.75rem (12px)
- `4` = 1rem (16px)
- ...etc.

## Cores e Fundos

### Cores de texto

```html
<p class="text-black">Texto preto</p>
<p class="text-white">Texto branco</p>
<p class="text-gray-500">Tons de cinza</p>
<p class="text-red-500">Cores primárias</p>
<p class="text-blue-700">Tons mais escuros</p>
<p class="text-green-300">Tons mais claros</p>
```

### Cores de fundo

```html
<div class="bg-white">Fundo branco</div>
<div class="bg-black">Fundo preto</div>
<div class="bg-blue-500">Fundo azul</div>
<div class="bg-opacity-50">Transparência 50%</div>
```

### Gradientes

```html
<div class="bg-gradient-to-r from-cyan-500 to-blue-500">
  Gradiente horizontal
</div>
<div class="bg-gradient-to-b from-purple-500 via-pink-500 to-red-500">
  Gradiente com ponto intermediário
</div>
```

## Dimensionamento

### Largura e Altura

```html
<div class="w-full">Largura 100%</div>
<div class="w-1/2">Largura 50%</div>
<div class="w-64">Largura 16rem (256px)</div>
<div class="w-auto">Largura automática</div>

<div class="h-screen">Altura 100vh</div>
<div class="h-64">Altura 16rem (256px)</div>
<div class="h-full">Altura 100%</div>
<div class="h-auto">Altura automática</div>
```

### Largura/Altura máxima e mínima

```html
<div class="max-w-md">Largura máxima média</div>
<div class="min-h-screen">Altura mínima de tela cheia</div>
```

## Tipografia

### Família da fonte

```html
<p class="font-sans">Fonte sans-serif</p>
<p class="font-serif">Fonte serifada</p>
<p class="font-mono">Fonte monoespaçada</p>
```

### Tamanho da fonte

```html
<p class="text-xs">Extra pequeno</p>
<p class="text-sm">Pequeno</p>
<p class="text-base">Base (16px)</p>
<p class="text-lg">Grande</p>
<p class="text-xl">Extra grande</p>
<p class="text-2xl">2x grande</p>
<!-- até text-9xl -->
```

### Peso da fonte

```html
<p class="font-thin">Thin</p>
<p class="font-light">Light</p>
<p class="font-normal">Normal</p>
<p class="font-medium">Medium</p>
<p class="font-semibold">Semibold</p>
<p class="font-bold">Bold</p>
<p class="font-extrabold">Extra Bold</p>
<p class="font-black">Black</p>
```

### Estilo e alinhamento de texto

```html
<p class="italic">Itálico</p>
<p class="underline">Sublinhado</p>
<p class="line-through">Tachado</p>
<p class="text-left">Alinhado à esquerda</p>
<p class="text-center">Centralizado</p>
<p class="text-right">Alinhado à direita</p>
<p class="text-justify">Justificado</p>
```

## Layouts

### Display

```html
<div class="block">Bloco</div>
<div class="inline">Em linha</div>
<div class="inline-block">Bloco em linha</div>
<div class="flex">Flexbox</div>
<div class="grid">Grid</div>
<div class="hidden">Oculto</div>
```

### Posicionamento

```html
<div class="static">Estático (padrão)</div>
<div class="relative">Relativo</div>
<div class="absolute">Absoluto</div>
<div class="fixed">Fixo</div>
<div class="sticky">Grudento</div>
```

## Bordas

### Arredondamento de bordas

```html
<div class="rounded">Arredondamento padrão</div>
<div class="rounded-sm">Pequeno</div>
<div class="rounded-md">Médio</div>
<div class="rounded-lg">Grande</div>
<div class="rounded-full">Circular</div>
<div class="rounded-t-lg">Apenas topo</div>
<div class="rounded-r-lg">Apenas direita</div>
<div class="rounded-b-lg">Apenas base</div>
<div class="rounded-l-lg">Apenas esquerda</div>
```

### Largura e estilo da borda

```html
<div class="border">Borda padrão</div>
<div class="border-2">Borda mais grossa</div>
<div class="border-t">Apenas topo</div>
<div class="border-r">Apenas direita</div>
<div class="border-b">Apenas base</div>
<div class="border-l">Apenas esquerda</div>

<div class="border-solid">Sólida (padrão)</div>
<div class="border-dashed">Tracejada</div>
<div class="border-dotted">Pontilhada</div>
```

### Cor da borda

```html
<div class="border border-blue-500">Borda azul</div>
<div class="border border-red-500">Borda vermelha</div>
```

## Sombras

```html
<div class="shadow-sm">Sombra pequena</div>
<div class="shadow">Sombra padrão</div>
<div class="shadow-md">Média</div>
<div class="shadow-lg">Grande</div>
<div class="shadow-xl">Extra grande</div>
<div class="shadow-2xl">2x grande</div>
<div class="shadow-inner">Sombra interna</div>
<div class="shadow-none">Sem sombra</div>
```

## Transições e Transformações

### Transições

```html
<button class="transition duration-150 ease-in-out">
  Transição padrão
</button>
<button class="transition-colors duration-300">
  Transição apenas de cores
</button>
```

### Duração e curva da transição

```html
<div class="duration-75">Rápida (75ms)</div>
<div class="duration-100">100ms</div>
<div class="duration-500">Média (500ms)</div>
<div class="duration-1000">Lenta (1000ms)</div>

<div class="ease-linear">Linear</div>
<div class="ease-in">Ease in</div>
<div class="ease-out">Ease out</div>
<div class="ease-in-out">Ease in-out</div>
```

### Transformações

```html
<div class="scale-75">Escala 75%</div>
<div class="scale-100">Escala normal</div>
<div class="scale-125">Escala 125%</div>

<div class="rotate-45">Rotação 45 graus</div>
<div class="rotate-90">Rotação 90 graus</div>

<div class="translate-x-4">Mover horizontalmente</div>
<div class="translate-y-4">Mover verticalmente</div>
<div class="skew-x-12">Inclinar no eixo X</div>
```

## Responsividade

O Tailwind inclui prefixos de breakpoint para aplicar utilitários em tamanhos de tela específicos:

```html
<!-- Aplicado em todas as telas -->
<div class="text-sm md:text-base lg:text-lg">
  Texto responsivo
</div>

<!-- Layout que muda de coluna para linha em telas médias -->
<div class="flex flex-col md:flex-row">
  <!-- Conteúdo aqui -->
</div>
```

- `sm`: Mínimo 640px
- `md`: Mínimo 768px
- `lg`: Mínimo 1024px
- `xl`: Mínimo 1280px
- `2xl`: Mínimo 1536px

## Encadeando Utilitários

A magia do Tailwind está na composição de utilitários para criar designs complexos:

```html
<button class="
  px-4 py-2 
  bg-blue-500 hover:bg-blue-700 
  text-white font-bold 
  rounded 
  transition duration-300">
  Botão Estilizado
</button>
```

Este botão combina espaçamento, cores, tipografia, bordas e transições.

## Padrões Comuns e Exemplos

### Card

```html
<div class="max-w-sm mx-auto bg-white rounded-xl shadow-md overflow-hidden md:max-w-2xl">
  <div class="md:flex">
    <div class="md:shrink-0">
      <img class="h-48 w-full object-cover md:h-full md:w-48" src="imagem.jpg" alt="Imagem">
    </div>
    <div class="p-8">
      <div class="uppercase tracking-wide text-sm text-indigo-500 font-semibold">Categoria</div>
      <a href="#" class="block mt-1 text-lg leading-tight font-medium text-black hover:underline">
        Título do Card
      </a>
      <p class="mt-2 text-gray-500">Descrição aqui...</p>
    </div>
  </div>
</div>
```

### Botão

```html
<button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">
  Clique Aqui
</button>
```

### Badge

```html
<span class="inline-flex items-center px-2.5 py-0.5 rounded-full text-xs font-medium bg-green-100 text-green-800">
  Novo
</span>
```

## Links Úteis

- [Documentação de utilitários](https://tailwindcss.com/docs/utility-first)
- [Cheat Sheet](https://nerdcave.com/tailwind-cheat-sheet)
- [Lista completa de classes](https://tailwindcss.com/docs/installation)

---

[⬅️ Voltar para o início](../README.md)

<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=06B6D4&height=120&section=footer"/>