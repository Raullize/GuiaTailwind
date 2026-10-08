<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=06B6D4&height=120&section=header&fontSize=30&fontColor=fff&animation=twinkling&fontAlignY=35"/>

# Componentes e Plugins no Tailwind CSS

O Tailwind CSS é um framework altamente extensível que permite criar componentes reutilizáveis e adicionar funcionalidades através de plugins. Esta seção mostra como aproveitar essas capacidades para melhorar seu fluxo de trabalho.

## Criando Componentes Reutilizáveis

Embora o Tailwind seja um framework utilitário, existem várias abordagens para criar componentes reutilizáveis.

### Abordagem 1: Extrair Componentes em HTML

A maneira mais simples é criar snippets HTML reutilizáveis:

```html
<!-- Botão primário -->
<button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">
  Botão Primário
</button>

<!-- Botão secundário -->
<button class="bg-gray-300 hover:bg-gray-400 text-gray-800 font-bold py-2 px-4 rounded">
  Botão Secundário
</button>
```

### Abordagem 2: Usando @apply em CSS

Para projetos maiores, você pode extrair classes repetitivas usando a diretiva `@apply`:

```css
/* src/styles/buttons.css */
.btn {
  @apply font-bold py-2 px-4 rounded;
}

.btn-primary {
  @apply bg-blue-500 text-white;
}

.btn-primary:hover {
  @apply bg-blue-700;
}

.btn-secondary {
  @apply bg-gray-300 text-gray-800;
}

.btn-secondary:hover {
  @apply bg-gray-400;
}
```

Uso no HTML:

```html
<button class="btn btn-primary">Botão Primário</button>
<button class="btn btn-secondary">Botão Secundário</button>
```

### Abordagem 3: Componentes em Frameworks JS

Em React, Vue ou outros frameworks, você pode criar componentes normalmente:

#### React

```jsx
// Button.jsx
function Button({ variant = 'primary', children, ...props }) {
  const baseClasses = 'font-bold py-2 px-4 rounded';
  
  const variantClasses = {
    primary: 'bg-blue-500 hover:bg-blue-700 text-white',
    secondary: 'bg-gray-300 hover:bg-gray-400 text-gray-800',
    success: 'bg-green-500 hover:bg-green-700 text-white',
    danger: 'bg-red-500 hover:bg-red-700 text-white',
  };
  
  return (
    <button 
      className={`${baseClasses} ${variantClasses[variant]}`}
      {...props}
    >
      {children}
    </button>
  );
}
```

#### Vue

```vue
<!-- Button.vue -->
<template>
  <button :class="classes">
    <slot></slot>
  </button>
</template>

<script>
export default {
  props: {
    variant: {
      type: String,
      default: 'primary'
    }
  },
  computed: {
    classes() {
      const baseClasses = 'font-bold py-2 px-4 rounded';
      
      const variantClasses = {
        primary: 'bg-blue-500 hover:bg-blue-700 text-white',
        secondary: 'bg-gray-300 hover:bg-gray-400 text-gray-800',
        success: 'bg-green-500 hover:bg-green-700 text-white',
        danger: 'bg-red-500 hover:bg-red-700 text-white',
      };
      
      return `${baseClasses} ${variantClasses[this.variant]}`;
    }
  }
}
</script>
```

## Criando Componentes Comuns

### 1. Card Responsivo

```html
<div class="bg-white rounded-lg overflow-hidden shadow-lg">
  <img class="w-full" src="image.jpg" alt="Card Image">
  <div class="p-6">
    <h3 class="font-bold text-xl mb-2">Título do Card</h3>
    <p class="text-gray-700 text-base">
      Conteúdo do card com descrição detalhada.
    </p>
  </div>
  <div class="px-6 pt-4 pb-6">
    <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">
      Ver mais
    </button>
  </div>
</div>
```

Com `@apply`:

```css
.card {
  @apply bg-white rounded-lg overflow-hidden shadow-lg;
}

.card-img {
  @apply w-full;
}

.card-body {
  @apply p-6;
}

.card-title {
  @apply font-bold text-xl mb-2;
}

.card-text {
  @apply text-gray-700 text-base;
}

.card-footer {
  @apply px-6 pt-4 pb-6;
}
```

### 2. Dropdown Menu

```html
<div class="relative inline-block text-left">
  <!-- Botão do Dropdown -->
  <button class="inline-flex justify-center w-full px-4 py-2 text-sm font-medium text-white bg-black rounded-md bg-opacity-20 hover:bg-opacity-30 focus:outline-none focus-visible:ring-2 focus-visible:ring-white focus-visible:ring-opacity-75">
    Opções
    <svg class="w-5 h-5 ml-2 -mr-1" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20" fill="currentColor">
      <path fill-rule="evenodd" d="M5.293 7.293a1 1 0 011.414 0L10 10.586l3.293-3.293a1 1 0 111.414 1.414l-4 4a1 1 0 01-1.414 0l-4-4a1 1 0 010-1.414z" clip-rule="evenodd" />
    </svg>
  </button>

  <!-- Itens do Dropdown -->
  <div class="absolute right-0 w-56 mt-2 origin-top-right bg-white divide-y divide-gray-100 rounded-md shadow-lg ring-1 ring-black ring-opacity-5 focus:outline-none">
    <div class="px-1 py-1">
      <a href="#" class="block px-4 py-2 text-sm text-gray-700 hover:bg-gray-100 hover:text-gray-900">Editar</a>
      <a href="#" class="block px-4 py-2 text-sm text-gray-700 hover:bg-gray-100 hover:text-gray-900">Duplicar</a>
    </div>
    <div class="px-1 py-1">
      <a href="#" class="block px-4 py-2 text-sm text-red-700 hover:bg-red-100 hover:text-red-900">Excluir</a>
    </div>
  </div>
</div>
```

### 3. Formulário de Contato

```html
<form class="max-w-md mx-auto p-6 bg-white rounded-lg shadow-md">
  <div class="mb-4">
    <label class="block text-gray-700 text-sm font-bold mb-2" for="name">
      Nome
    </label>
    <input class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:ring focus:border-blue-500" id="name" type="text" placeholder="Seu nome">
  </div>
  
  <div class="mb-4">
    <label class="block text-gray-700 text-sm font-bold mb-2" for="email">
      Email
    </label>
    <input class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:ring focus:border-blue-500" id="email" type="email" placeholder="seu@email.com">
  </div>
  
  <div class="mb-6">
    <label class="block text-gray-700 text-sm font-bold mb-2" for="message">
      Mensagem
    </label>
    <textarea class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:ring focus:border-blue-500" id="message" rows="4" placeholder="Sua mensagem"></textarea>
  </div>
  
  <div class="flex items-center justify-between">
    <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded focus:outline-none focus:shadow-outline" type="submit">
      Enviar Mensagem
    </button>
  </div>
</form>
```

## Plugins Oficiais do Tailwind

### 1. @tailwindcss/forms

Estiliza elementos de formulário para uma experiência melhor e mais consistente.

Instalação:

```bash
npm install @tailwindcss/forms
```

Configuração:

```javascript
// tailwind.config.js
module.exports = {
  // ...
  plugins: [
    require('@tailwindcss/forms'),
    // ...
  ],
}
```

Exemplo:

```html
<!-- Input estilizado automaticamente -->
<input type="text" class="border-gray-300 rounded-md">
<input type="checkbox" class="rounded text-blue-500">
<select class="rounded-md border-gray-300">
  <option>Opção 1</option>
  <option>Opção 2</option>
</select>
```

### 2. @tailwindcss/typography

Fornece estilos para conteúdo tipográfico (útil para conteúdo de blogs, CMS ou Markdown).

Instalação:

```bash
npm install @tailwindcss/typography
```

Configuração:

```javascript
// tailwind.config.js
module.exports = {
  // ...
  plugins: [
    require('@tailwindcss/typography'),
    // ...
  ],
}
```

Exemplo:

```html
<article class="prose lg:prose-xl">
  <h1>Heading 1</h1>
  <p>Parágrafo com <em>ênfase</em> e <strong>texto forte</strong>.</p>
  <ul>
    <li>Item 1</li>
    <li>Item 2</li>
  </ul>
  <blockquote>Citação importante</blockquote>
</article>
```

### 3. @tailwindcss/aspect-ratio

Ajuda a manter as proporções de aspecto consistentes em elementos responsivos.

Instalação:

```bash
npm install @tailwindcss/aspect-ratio
```

Configuração:

```javascript
// tailwind.config.js
module.exports = {
  // ...
  plugins: [
    require('@tailwindcss/aspect-ratio'),
    // ...
  ],
}
```

Exemplo:

```html
<!-- Proporção 16:9 -->
<div class="aspect-w-16 aspect-h-9">
  <img src="image.jpg" alt="Imagem" class="object-cover">
</div>

<!-- Proporção 4:3 -->
<div class="aspect-w-4 aspect-h-3">
  <iframe src="https://www.youtube.com/embed/dQw4w9WgXcQ" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>
```

### 4. @tailwindcss/line-clamp

Trunca texto em um número específico de linhas.

Instalação:

```bash
npm install @tailwindcss/line-clamp
```

Configuração:

```javascript
// tailwind.config.js
module.exports = {
  // ...
  plugins: [
    require('@tailwindcss/line-clamp'),
    // ...
  ],
}
```

Exemplo:

```html
<!-- Limita o texto a 3 linhas -->
<p class="line-clamp-3">
  Este é um texto longo que será truncado após três linhas. 
  Qualquer texto além do limite será substituído por reticências.
  Esta linha e as seguintes não serão exibidas.
  Esta linha também não aparecerá.
</p>

<!-- Valores disponíveis: line-clamp-1 até line-clamp-6 -->
```

## Criando Plugins Personalizados

Você pode criar seus próprios plugins para adicionar funcionalidades específicas.

### Estrutura Básica de um Plugin

```javascript
// meu-plugin.js
const plugin = require('tailwindcss/plugin')

module.exports = plugin(function({ addUtilities, addComponents, theme, variants }) {
  // Adicionar utilitários
  // Adicionar componentes
  // Estender o tema
})
```

### Exemplo: Plugin para Sombras de Texto

```javascript
// text-shadow-plugin.js
const plugin = require('tailwindcss/plugin')

module.exports = plugin(function({ addUtilities, theme }) {
  const newUtilities = {
    '.text-shadow-sm': {
      textShadow: '0 1px 2px rgba(0, 0, 0, 0.05)',
    },
    '.text-shadow': {
      textShadow: '0 2px 4px rgba(0, 0, 0, 0.1)',
    },
    '.text-shadow-lg': {
      textShadow: '0 4px 8px rgba(0, 0, 0, 0.12), 0 2px 4px rgba(0, 0, 0, 0.08)',
    },
    '.text-shadow-none': {
      textShadow: 'none',
    },
  }

  addUtilities(newUtilities, ['responsive', 'hover'])
})
```

Configuração:

```javascript
// tailwind.config.js
module.exports = {
  // ...
  plugins: [
    require('./text-shadow-plugin'),
    // ...
  ],
}
```

Uso:

```html
<h1 class="text-4xl text-white text-shadow-lg">Título com Sombra</h1>
<p class="text-shadow hover:text-shadow-lg">Texto com sombra que aumenta no hover</p>
```

### Exemplo: Plugin para Gradientes Personalizados

```javascript
// gradients-plugin.js
const plugin = require('tailwindcss/plugin')

module.exports = plugin(function({ addComponents, theme }) {
  const gradients = {
    '.gradient-blue-green': {
      background: 'linear-gradient(90deg, #4F46E5 0%, #10B981 100%)',
    },
    '.gradient-purple-pink': {
      background: 'linear-gradient(90deg, #8B5CF6 0%, #EC4899 100%)',
    },
    '.gradient-orange-yellow': {
      background: 'linear-gradient(90deg, #F97316 0%, #FACC15 100%)',
    },
    '.gradient-gray': {
      background: 'linear-gradient(180deg, #FFFFFF 0%, #F3F4F6 100%)',
    },
  }

  addComponents(gradients)
})
```

Uso:

```html
<div class="gradient-purple-pink text-white p-6 rounded-lg">
  <h2 class="text-xl font-bold">Título com Gradiente</h2>
  <p>Conteúdo com fundo em gradiente.</p>
</div>
```

## Ferramentas e Recursos de Componentes

### 1. Bibliotecas de Componentes

- **Tailwind UI**: Componentes premium mantidos pela equipe do Tailwind
- **DaisyUI**: Componentes gratuitos para Tailwind CSS
- **Flowbite**: Componentes de UI baseados em Tailwind
- **Headless UI**: Componentes sem estilo mas com funcionalidade
- **Tailblocks**: Blocos e seções prontas para uso

### 2. Geradores de Componentes

- **Tailwind Components**: Coleção de componentes
- **Tailwind Toolbox**: Templates e recursos para Tailwind
- **Kometa UI Kit**: Kit de UI para Tailwind
- **Meraki UI**: Componentes bonitos para Tailwind CSS
- **Tailwind Templates**: Templates de páginas inteiras

### 3. Integrações com Frameworks

#### React
- **twin.macro**: Styled-components + Tailwind
- **@headlessui/react**: Componentes de UI acessíveis

#### Vue
- **@headlessui/vue**: Componentes de UI acessíveis
- **VueTailwind**: Biblioteca de componentes Vue

#### Angular
- **ng-tailwindcss**: Integração do Tailwind com Angular
- **tailwindcss-schematic**: Adiciona Tailwind a projetos Angular

## Exemplos Práticos de Componentes Reutilizáveis

### Sistema de Alertas

```html
<!-- Alerta de Sucesso -->
<div class="p-4 mb-4 text-sm rounded-lg bg-green-100 text-green-700">
  <div class="font-medium">Sucesso!</div>
  <div>Sua ação foi realizada com sucesso.</div>
</div>

<!-- Alerta de Erro -->
<div class="p-4 mb-4 text-sm rounded-lg bg-red-100 text-red-700">
  <div class="font-medium">Erro!</div>
  <div>Ocorreu um problema ao processar sua solicitação.</div>
</div>

<!-- Alerta de Informação -->
<div class="p-4 mb-4 text-sm rounded-lg bg-blue-100 text-blue-700">
  <div class="font-medium">Informação</div>
  <div>Esta é uma mensagem informativa.</div>
</div>

<!-- Alerta Dismissível com JavaScript -->
<div id="alert" class="p-4 mb-4 flex justify-between items-start text-sm rounded-lg bg-yellow-100 text-yellow-700">
  <div>
    <div class="font-medium">Atenção!</div>
    <div>Esta é uma mensagem de aviso importante.</div>
  </div>
  <button onclick="document.getElementById('alert').style.display = 'none'" class="ml-4">
    <svg class="w-4 h-4" fill="currentColor" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg">
      <path fill-rule="evenodd" d="M4.293 4.293a1 1 0 011.414 0L10 8.586l4.293-4.293a1 1 0 111.414 1.414L11.414 10l4.293 4.293a1 1 0 01-1.414 1.414L10 11.414l-4.293 4.293a1 1 0 01-1.414-1.414L8.586 10 4.293 5.707a1 1 0 010-1.414z" clip-rule="evenodd"></path>
    </svg>
  </button>
</div>
```

### Modal

```html
<!-- Botão para abrir o modal -->
<button onclick="document.getElementById('modal').classList.remove('hidden')" class="bg-blue-500 hover:bg-blue-600 text-white px-4 py-2 rounded">
  Abrir Modal
</button>

<!-- Modal -->
<div id="modal" class="hidden fixed inset-0 overflow-y-auto flex items-center justify-center z-50">
  <!-- Overlay de fundo -->
  <div class="fixed inset-0 bg-black opacity-50"></div>
  
  <!-- Conteúdo do modal -->
  <div class="bg-white rounded-lg shadow-xl p-6 max-w-md mx-auto z-10 relative">
    <div class="flex justify-between items-center mb-4">
      <h3 class="text-lg font-medium">Título do Modal</h3>
      <button onclick="document.getElementById('modal').classList.add('hidden')" class="text-gray-400 hover:text-gray-600">
        <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"></path>
        </svg>
      </button>
    </div>
    
    <div class="my-4">
      <p>Conteúdo do modal vai aqui. Você pode incluir texto, imagens ou qualquer outro elemento HTML.</p>
    </div>
    
    <div class="mt-6 flex justify-end space-x-3">
      <button onclick="document.getElementById('modal').classList.add('hidden')" class="px-4 py-2 bg-gray-200 hover:bg-gray-300 rounded text-gray-800">
        Cancelar
      </button>
      <button class="px-4 py-2 bg-blue-500 hover:bg-blue-600 rounded text-white">
        Confirmar
      </button>
    </div>
  </div>
</div>
```

### Tabs

```html
<div>
  <!-- Tab Headers -->
  <div class="border-b border-gray-200">
    <nav class="flex -mb-px">
      <button onclick="openTab('tab1')" class="tab-btn active-tab" id="tab1-btn">
        Aba 1
      </button>
      <button onclick="openTab('tab2')" class="tab-btn" id="tab2-btn">
        Aba 2
      </button>
      <button onclick="openTab('tab3')" class="tab-btn" id="tab3-btn">
        Aba 3
      </button>
    </nav>
  </div>
  
  <!-- Tab Contents -->
  <div class="py-4">
    <div id="tab1" class="tab-content">
      <p>Conteúdo da primeira aba.</p>
    </div>
    <div id="tab2" class="tab-content hidden">
      <p>Conteúdo da segunda aba.</p>
    </div>
    <div id="tab3" class="tab-content hidden">
      <p>Conteúdo da terceira aba.</p>
    </div>
  </div>
</div>

<style>
  .tab-btn {
    @apply px-4 py-2 font-medium text-sm text-gray-500 hover:text-gray-700 border-b-2 border-transparent;
  }
  .active-tab {
    @apply border-blue-500 text-blue-600;
  }
</style>

<script>
  function openTab(tabId) {
    // Esconder todos os conteúdos
    const contents = document.querySelectorAll('.tab-content');
    contents.forEach(content => content.classList.add('hidden'));
    
    // Mostrar o conteúdo selecionado
    document.getElementById(tabId).classList.remove('hidden');
    
    // Atualizar estados dos botões
    const buttons = document.querySelectorAll('.tab-btn');
    buttons.forEach(button => button.classList.remove('active-tab'));
    document.getElementById(tabId + '-btn').classList.add('active-tab');
  }
</script>
```

## Links Úteis

- [Documentação oficial de Plugins](https://tailwindcss.com/docs/plugins)
- [Tailwind UI](https://tailwindui.com/) (Componentes premium)
- [Headless UI](https://headlessui.dev/) (Componentes sem estilo)
- [DaisyUI](https://daisyui.com/) (Componentes gratuitos)
- [Meraki UI](https://merakiui.com/) (Componentes gratuitos)
- [Tailwind Components](https://tailwindcomponents.com/) (Comunidade de componentes)

---

[⬅️ Voltar para o início](../README.md)

<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=06B6D4&height=120&section=footer"/>