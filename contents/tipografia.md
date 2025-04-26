<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=06B6D4&height=120&section=header&fontSize=30&fontColor=fff&animation=twinkling&fontAlignY=35"/>

# 🖼️ Tipografia no Tailwind CSS 📝

O Tailwind CSS oferece um conjunto completo de utilitários para estilizar texto, permitindo controlar fontes, tamanhos, pesos, espaçamentos e muito mais. Esta seção explora as classes relacionadas à tipografia e como utilizá-las.

## 📊 Família de Fontes

O Tailwind possui algumas famílias de fontes padrão que você pode personalizar no arquivo de configuração.

```html
<p class="font-sans">Inter, Helvetica, Arial, sans-serif</p>
<p class="font-serif">ui-serif, Georgia, Cambria, Times New Roman, Times, serif</p>
<p class="font-mono">ui-monospace, SFMono-Regular, Menlo, Monaco, Consolas, monospace</p>
```

### Configurando Fontes Personalizadas

Para adicionar suas próprias fontes no `tailwind.config.js`:

```javascript
module.exports = {
  theme: {
    fontFamily: {
      'sans': ['Poppins', 'system-ui', 'sans-serif'],
      'serif': ['Merriweather', 'serif'],
      'mono': ['JetBrains Mono', 'monospace'],
      // Fontes personalizadas
      'display': ['Oswald', 'sans-serif'],
      'body': ['Open Sans', 'sans-serif'],
    }
  }
}
```

Uso:

```html
<h1 class="font-display">Título com Oswald</h1>
<p class="font-body">Texto com Open Sans</p>
```

## 📏 Tamanho da Fonte

O Tailwind oferece uma escala de tamanhos de fonte consistente:

```html
<p class="text-xs">Tamanho extra pequeno (0.75rem)</p>
<p class="text-sm">Tamanho pequeno (0.875rem)</p>
<p class="text-base">Tamanho base (1rem)</p>
<p class="text-lg">Tamanho grande (1.125rem)</p>
<p class="text-xl">Tamanho extra grande (1.25rem)</p>
<p class="text-2xl">2x grande (1.5rem)</p>
<p class="text-3xl">3x grande (1.875rem)</p>
<p class="text-4xl">4x grande (2.25rem)</p>
<p class="text-5xl">5x grande (3rem)</p>
<p class="text-6xl">6x grande (3.75rem)</p>
<p class="text-7xl">7x grande (4.5rem)</p>
<p class="text-8xl">8x grande (6rem)</p>
<p class="text-9xl">9x grande (8rem)</p>
```

## 🔤 Peso da Fonte

Controle o peso (espessura) da fonte:

```html
<p class="font-thin">Peso 100</p>
<p class="font-extralight">Peso 200</p>
<p class="font-light">Peso 300</p>
<p class="font-normal">Peso 400 (normal)</p>
<p class="font-medium">Peso 500</p>
<p class="font-semibold">Peso 600</p>
<p class="font-bold">Peso 700</p>
<p class="font-extrabold">Peso 800</p>
<p class="font-black">Peso 900</p>
```

## 📐 Espaçamento de Letras

O espaçamento entre letras (tracking):

```html
<p class="tracking-tighter">Tracking mais apertado (-0.05em)</p>
<p class="tracking-tight">Tracking apertado (-0.025em)</p>
<p class="tracking-normal">Tracking normal (0em)</p>
<p class="tracking-wide">Tracking amplo (0.025em)</p>
<p class="tracking-wider">Tracking mais amplo (0.05em)</p>
<p class="tracking-widest">Tracking super amplo (0.1em)</p>
```

## 📏 Altura da Linha

A altura da linha (line-height) controla o espaçamento vertical entre linhas:

```html
<p class="leading-none">Altura de linha 1 (sem espaço)</p>
<p class="leading-tight">Altura de linha apertada (1.25)</p>
<p class="leading-snug">Altura de linha confortável (1.375)</p>
<p class="leading-normal">Altura de linha normal (1.5)</p>
<p class="leading-relaxed">Altura de linha relaxada (1.625)</p>
<p class="leading-loose">Altura de linha solta (2)</p>
<!-- Valores específicos -->
<p class="leading-3">Line height 0.75rem (12px)</p>
<p class="leading-4">Line height 1rem (16px)</p>
<!-- E assim por diante até leading-10 -->
```

## 🔠 Transformação de Texto

```html
<p class="uppercase">TEXTO EM MAIÚSCULAS</p>
<p class="lowercase">texto em minúsculas</p>
<p class="capitalize">Cada Palavra Com Inicial Maiúscula</p>
<p class="normal-case">Texto normal sem transformação</p>
```

## 📌 Decoração de Texto

```html
<p class="underline">Texto sublinhado</p>
<p class="overline">Texto com linha superior</p>
<p class="line-through">Texto tachado</p>
<p class="no-underline">Sem decoração</p>
```

## 📊 Alinhamento de Texto

```html
<p class="text-left">Alinhado à esquerda</p>
<p class="text-center">Alinhado ao centro</p>
<p class="text-right">Alinhado à direita</p>
<p class="text-justify">Texto justificado que preenche a largura do container distribuindo as palavras uniformemente.</p>
<p class="text-start">Início lógico (depende da direção do texto)</p>
<p class="text-end">Fim lógico (depende da direção do texto)</p>
```

## 📏 Identação

A identação da primeira linha:

```html
<p class="indent-0">Sem identação</p>
<p class="indent-1">Identação pequena (0.25rem)</p>
<p class="indent-2">Identação média (0.5rem)</p>
<p class="indent-4">Identação grande (1rem)</p>
<p class="indent-8">Identação extra grande (2rem)</p>
```

## 📜 Quebra de Texto e Overflow

### Quebra de Palavras

```html
<p class="break-normal">Quebra de linha e palavras normal</p>
<p class="break-words">Quebra palavras longas que ultrapassariam o container</p>
<p class="break-all">Quebra todas as palavras, mesmo dentro de palavras</p>
<p class="break-keep">Mantém palavras inteiras</p>
```

### Truncamento de Texto

```html
<p class="truncate">Texto truncado com reticências quando não cabe em uma linha...</p>
<p class="text-ellipsis">Ellipsis com overflow</p>
<p class="text-clip">Corta o texto sem ellipsis</p>
```

## 📐 Espaço Entre Palavras

```html
<p class="whitespace-normal">Espaçamento normal</p>
<p class="whitespace-nowrap">Texto não quebra em novas linhas</p>
<p class="whitespace-pre">Preserva espaços e quebras de linha</p>
<p class="whitespace-pre-line">Preserva quebras de linha, mas não múltiplos espaços</p>
<p class="whitespace-pre-wrap">Preserva espaços e quebras, mas permite quebras automáticas</p>
```

## 🖌️ Estilo de Fonte

```html
<p class="italic">Texto em itálico</p>
<p class="not-italic">Texto sem itálico</p>
```

## 🧬 Variantes de Fonte

Se você estiver usando fontes variáveis, o Tailwind também oferece suporte:

```html
<p class="font-sans font-variation-settings:['wght' 900]">
  Texto com variação de peso 900
</p>
```

## 📘 Direção do Texto

```html
<p class="rtl">Texto da direita para a esquerda</p>
<p class="ltr">Texto da esquerda para a direita</p>
```

## 🎯 Lista de Marcadores

```html
<ul class="list-disc">
  <li>Item com marcador circular</li>
</ul>

<ul class="list-decimal">
  <li>Item com numeração</li>
</ul>

<ul class="list-none">
  <li>Item sem marcador</li>
</ul>
```

## 🎨 Cores de Texto

O Tailwind oferece uma ampla paleta de cores para texto:

```html
<p class="text-black">Texto preto</p>
<p class="text-white">Texto branco</p>
<p class="text-gray-500">Texto cinza médio</p>
<p class="text-red-600">Texto vermelho</p>
<p class="text-blue-400">Texto azul</p>
<p class="text-green-700">Texto verde escuro</p>
<p class="text-yellow-300">Texto amarelo claro</p>
<!-- E muitas outras combinações -->
```

## 📱 Responsividade na Tipografia

Adapte a tipografia para diferentes tamanhos de tela:

```html
<h1 class="text-xl sm:text-2xl md:text-3xl lg:text-4xl xl:text-5xl">
  Título responsivo
</h1>

<p class="text-sm md:text-base lg:text-lg">
  Parágrafo com tamanho responsivo
</p>
```

## 🎭 Estados e Variantes

Aplique estilos de texto em diferentes estados:

```html
<button class="text-blue-500 hover:text-blue-700 focus:text-blue-800">
  Botão com texto que muda de cor
</button>

<a class="text-gray-700 hover:text-black hover:underline">
  Link com sublinhado ao passar o mouse
</a>
```

## 🛠️ Exemplos Práticos

### Cabeçalho de Artigo

```html
<header>
  <h1 class="font-serif text-3xl md:text-4xl font-bold text-gray-900 leading-tight">
    Título Principal do Artigo Que Pode Ocupar Duas Linhas
  </h1>
  <div class="mt-2 text-sm text-gray-500">
    <span class="font-medium">John Doe</span>
    <span class="mx-1">•</span>
    <span>12 de Maio, 2023</span>
    <span class="mx-1">•</span>
    <span>8 min de leitura</span>
  </div>
</header>
```

### Card de Produto

```html
<div class="max-w-md bg-white rounded-lg overflow-hidden shadow-lg">
  <img src="product.jpg" alt="Produto" class="w-full h-48 object-cover">
  <div class="p-4">
    <span class="text-sm font-semibold uppercase tracking-wide text-indigo-500">Novo</span>
    <h2 class="mt-2 text-xl font-bold text-gray-900 leading-tight truncate">
      Nome do Produto Premium
    </h2>
    <p class="mt-2 text-gray-600 text-sm leading-relaxed line-clamp-3">
      Descrição detalhada do produto que pode ocupar várias linhas e será truncada após três linhas com reticências...
    </p>
    <div class="mt-4 flex items-end justify-between">
      <div>
        <span class="text-lg font-bold text-gray-900">R$ 199,99</span>
        <span class="ml-1 text-sm text-gray-500 line-through">R$ 249,99</span>
      </div>
      <button class="bg-indigo-600 text-white text-sm font-medium py-2 px-4 rounded-lg hover:bg-indigo-700">
        Comprar
      </button>
    </div>
  </div>
</div>
```

### Citação

```html
<blockquote class="relative p-4 text-xl italic font-medium text-gray-900 border-l-4 border-gray-800 bg-gray-50">
  <div class="mb-4 text-gray-600">
    <svg class="w-8 h-8 text-gray-400 mb-4" fill="currentColor" viewBox="0 0 24 24">
      <path d="M14.017 21v-7.391c0-5.704 3.731-9.57 8.983-10.609l.995 2.151c-2.432.917-3.995 3.638-3.995 5.849h4v10h-9.983zm-14.017 0v-7.391c0-5.704 3.748-9.57 9-10.609l.996 2.151c-2.433.917-3.996 3.638-3.996 5.849h3.983v10h-9.983z" />
    </svg>
    A tipografia é a arte e técnica de organizar e desenhar letras de forma a tornar a linguagem escrita legível, clara e visualmente atraente.
  </div>
  <cite class="block text-sm font-bold text-gray-900 not-italic">
    — Robert Bringhurst, <span class="font-normal">The Elements of Typographic Style</span>
  </cite>
</blockquote>
```

### Título com Sublinhado Decorativo

```html
<h2 class="inline-block text-2xl font-bold text-gray-800 border-b-4 border-blue-500 pb-1">
  Seção do Conteúdo
</h2>
```

## 🎛️ Personalização Tipográfica

No `tailwind.config.js`, você pode personalizar todos os aspectos da tipografia:

```javascript
module.exports = {
  theme: {
    fontFamily: {
      'sans': ['Roboto', 'sans-serif'],
      'heading': ['Montserrat', 'sans-serif'],
      'mono': ['Fira Code', 'monospace'],
    },
    fontSize: {
      'xs': ['0.75rem', { lineHeight: '1rem' }],
      'sm': ['0.875rem', { lineHeight: '1.25rem' }],
      'base': ['1rem', { lineHeight: '1.5rem' }],
      'lg': ['1.125rem', { lineHeight: '1.75rem' }],
      'xl': ['1.25rem', { lineHeight: '1.75rem' }],
      '2xl': ['1.5rem', { lineHeight: '2rem' }],
      '3xl': ['1.875rem', { lineHeight: '2.25rem' }],
      // ... outros tamanhos
    },
    extend: {
      letterSpacing: {
        'super-wide': '0.15em',
      },
      lineHeight: {
        'extra-loose': '2.5',
      }
    }
  }
}
```

## 📚 Usando @apply para Componentes Reutilizáveis

Você pode usar a diretiva `@apply` para criar estilos de texto reutilizáveis:

```css
/* Em seu arquivo CSS */
.heading-1 {
  @apply text-3xl md:text-4xl font-bold text-gray-900 leading-tight;
}

.body-text {
  @apply text-base text-gray-700 leading-relaxed;
}

.caption {
  @apply text-sm text-gray-500 italic;
}
```

Uso:

```html
<h1 class="heading-1">Título Principal</h1>
<p class="body-text">Conteúdo do texto...</p>
<figcaption class="caption">Legenda da imagem</figcaption>
```

## 🧰 Plugin de Tipografia (Typography Plugin)

O Tailwind oferece um plugin oficial de tipografia para estilizar conteúdo de texto longo (como artigos, blog posts, etc.):

```bash
npm install @tailwindcss/typography
```

Configuração:

```javascript
// tailwind.config.js
module.exports = {
  plugins: [
    require('@tailwindcss/typography'),
  ],
}
```

Uso:

```html
<article class="prose lg:prose-xl">
  <h1>Título do Artigo</h1>
  <p>Parágrafo com conteúdo...</p>
  <ul>
    <li>Item da lista</li>
    <li>Outro item</li>
  </ul>
  <!-- Todo o conteúdo HTML dentro será estilizado automaticamente -->
</article>
```

## 🔗 Links Úteis

- [Documentação de Tipografia no Tailwind](https://tailwindcss.com/docs/font-family)
- [Plugin Typography](https://tailwindcss.com/docs/typography-plugin)
- [Personalizando Fontes](https://tailwindcss.com/docs/theme#customizing-the-default-theme)
- [Melhores práticas de tipografia web](https://css-tricks.com/typography-for-developers/)

---

[⬅️ Voltar para o início](../README.md)

<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=06B6D4&height=120&section=footer"/> 