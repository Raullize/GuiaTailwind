<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=06B6D4&height=120&section=header&fontSize=30&fontColor=fff&animation=twinkling&fontAlignY=35"/>

# 📱 Responsividade no Tailwind CSS 📲

A responsividade é uma característica essencial para qualquer projeto web moderno. O Tailwind CSS oferece um sistema poderoso e intuitivo para criar layouts que se adaptam perfeitamente a diferentes tamanhos de tela.

## 📏 Breakpoints Padrão

O Tailwind vem com cinco breakpoints padrão, inspirados em tamanhos comuns de dispositivos:

| Prefixo | Largura mínima | Exemplo de dispositivo |
|---------|---------------|------------------------|
| `sm`    | 640px         | Smartphones grandes    |
| `md`    | 768px         | Tablets                |
| `lg`    | 1024px        | Laptops                |
| `xl`    | 1280px        | Desktops               |
| `2xl`   | 1536px        | Telas grandes          |

## 🔄 Como Funciona

A abordagem do Tailwind para responsividade é **mobile-first**. Isso significa que:

1. Classes sem prefixo se aplicam a todas as tamanhos de tela
2. Classes com prefixo (ex: `md:`) se aplicam apenas daquele breakpoint para cima

```html
<div class="text-sm md:text-base lg:text-lg">
  <!-- 
    - Em telas menores que 768px: text-sm
    - De 768px a 1023px: text-base 
    - 1024px ou mais: text-lg
  -->
</div>
```

## 📋 Usando Prefixos Responsivos

Você pode adicionar prefixos responsivos à maioria das classes utilitárias do Tailwind:

### Layout Responsivo

```html
<!-- Muda de uma coluna em telas pequenas para duas colunas em médias e três em grandes -->
<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4">
  <div>Item 1</div>
  <div>Item 2</div>
  <div>Item 3</div>
  <div>Item 4</div>
  <div>Item 5</div>
  <div>Item 6</div>
</div>

<!-- Flexbox responsivo -->
<div class="flex flex-col md:flex-row">
  <div class="w-full md:w-1/3">Sidebar</div>
  <div class="w-full md:w-2/3">Conteúdo principal</div>
</div>
```

### Visibilidade Responsiva

```html
<!-- Visível apenas em dispositivos móveis -->
<div class="block md:hidden">
  Menu Mobile
</div>

<!-- Visível apenas em telas maiores -->
<div class="hidden md:block">
  Menu Desktop
</div>
```

### Tamanho e Espaçamento Responsivos

```html
<!-- Padding que aumenta com o tamanho da tela -->
<div class="p-2 sm:p-4 md:p-6 lg:p-8">
  Conteúdo com padding adaptativo
</div>

<!-- Margens responsivas -->
<div class="mx-2 sm:mx-4 md:mx-auto md:max-w-2xl lg:max-w-4xl">
  Container responsivo com largura máxima
</div>
```

### Tipografia Responsiva

```html
<!-- Tamanho de fonte que se adapta à tela -->
<h1 class="text-2xl sm:text-3xl md:text-4xl lg:text-5xl">
  Título Responsivo
</h1>

<!-- Alinhamento de texto responsivo -->
<p class="text-center md:text-left">
  Este texto é centralizado em celulares e alinhado à esquerda em telas maiores.
</p>
```

## 🎯 Customização de Breakpoints

Você pode personalizar os breakpoints no arquivo `tailwind.config.js`:

```javascript
// tailwind.config.js
module.exports = {
  theme: {
    screens: {
      'xs': '480px',
      'sm': '640px',
      'md': '768px',
      'lg': '1024px',
      'xl': '1280px',
      '2xl': '1536px',
      // Breakpoints personalizados
      'tablet': '992px',
      'desktop': '1200px',
      'widescreen': '1400px',
    }
  }
}
```

Você também pode definir breakpoints com base em intervalos:

```javascript
module.exports = {
  theme: {
    screens: {
      'sm': '640px',
      'md': '768px',
      'lg': '1024px',
      // Apenas para tablets (de 768px a 1023px)
      'tablet-only': {'min': '768px', 'max': '1023px'},
      // Apenas para dispositivos com altura maior que 800px
      'tall': {'raw': '(min-height: 800px)'},
    }
  }
}
```

## 📱 Mobile-First vs. Desktop-First

O Tailwind usa a abordagem **mobile-first** por padrão, mas você pode usar breakpoints com `max-width` para uma abordagem desktop-first:

```javascript
// tailwind.config.js
module.exports = {
  theme: {
    screens: {
      // Desktop-first
      '2xl-down': {'max': '1535px'},
      'xl-down': {'max': '1279px'},
      'lg-down': {'max': '1023px'},
      'md-down': {'max': '767px'},
      'sm-down': {'max': '639px'},
    }
  }
}
```

Uso:

```html
<div class="text-lg md-down:text-base sm-down:text-sm">
  <!-- 
    - Padrão (todas as telas): text-lg
    - Em telas menores que 768px: text-base
    - Em telas menores que 640px: text-sm
  -->
</div>
```

## 📦 Container Responsivo

O Tailwind inclui uma classe `container` para criar layouts responsivos:

```html
<!-- Container básico -->
<div class="container">
  Conteúdo
</div>

<!-- Container centralizado -->
<div class="container mx-auto">
  Conteúdo centralizado
</div>

<!-- Container com padding -->
<div class="container mx-auto px-4">
  Conteúdo com padding horizontal
</div>
```

Por padrão, o `container` tem estas larguras máximas:
- `sm`: 640px
- `md`: 768px
- `lg`: 1024px
- `xl`: 1280px
- `2xl`: 1536px

Você pode personalizar este comportamento:

```javascript
// tailwind.config.js
module.exports = {
  theme: {
    container: {
      center: true, // Centraliza automaticamente
      padding: {
        DEFAULT: '1rem',
        sm: '2rem',
        lg: '4rem',
        xl: '5rem',
      },
      screens: {
        sm: '600px',
        md: '728px',
        lg: '984px',
        xl: '1240px',
        '2xl': '1496px',
      }
    }
  }
}
```

## 🔍 Media Queries Personalizadas

Quando você precisa de lógica mais complexa, pode usar `@media` com a função `theme()`:

```css
/* Em seu CSS personalizado */
@media (min-width: theme('screens.lg')) {
  .selector {
    /* Estilos para telas grandes */
  }
}

@media (max-width: calc(theme('screens.md') - 1px)) {
  .selector {
    /* Estilos apenas para celulares */
  }
}
```

## 🖥️ Estratégias Avançadas

### Utilitários Responsivos Personalizados

```javascript
// tailwind.config.js
module.exports = {
  theme: {
    extend: {
      spacing: {
        'responsive-padding': 'clamp(1rem, 5vw, 3rem)',
      },
      fontSize: {
        'fluid-title': 'clamp(1.5rem, 5vw, 3rem)',
      }
    }
  }
}
```

### Focando em Orientação de Tela

```javascript
// tailwind.config.js
module.exports = {
  theme: {
    screens: {
      // Breakpoints padrão...
      
      'portrait': {'raw': '(orientation: portrait)'},
      'landscape': {'raw': '(orientation: landscape)'},
    }
  }
}
```

Uso:

```html
<div class="h-screen landscape:h-auto">
  <!-- Altura de tela cheia no modo retrato, automática no modo paisagem -->
</div>
```

## 🎯 Técnicas Responsivas Modernas

### Unidades Relativas

Combine unidades fixas e relativas para layouts mais resilientes:

```html
<!-- Contêiner que usa clamp() para largura responsiva -->
<div class="w-[clamp(300px,80vw,1200px)] mx-auto">
  Largura adaptativa entre 300px e 1200px
</div>

<!-- Altura mínima responsiva -->
<div class="min-h-[400px] md:min-h-[600px]">
  Altura mínima responsiva
</div>
```

### CSS Grid Auto-Fit/Auto-Fill

Use valores arbitrários para grid templates mais flexíveis:

```html
<!-- Grid responsivo sem media queries usando auto-fit -->
<div class="grid grid-cols-[repeat(auto-fit,minmax(250px,1fr))] gap-4">
  <div>Item 1</div>
  <div>Item 2</div>
  <div>Item 3</div>
  <div>Item 4</div>
  <div>Item 5</div>
  <div>Item 6</div>
</div>
```

### Container Queries

No Tailwind v3.3+, você pode usar Container Queries:

```html
<!-- Container para consulta -->
<div class="@container">
  <!-- 
    Item que se adapta ao tamanho do container, não da viewport 
    Exige plugin @tailwindcss/container-queries
  -->
  <div class="@md:flex @md:gap-6">
    <div class="@md:w-1/2">Coluna 1</div>
    <div class="@md:w-1/2">Coluna 2</div>
  </div>
</div>
```

Configurando o plugin:

```javascript
// tailwind.config.js
module.exports = {
  plugins: [
    require('@tailwindcss/container-queries'),
  ],
}
```

## 🛠️ Exemplos Práticos

### 1. Cabeçalho Responsivo

```html
<header class="bg-white shadow">
  <div class="container mx-auto px-4">
    <div class="flex flex-col md:flex-row md:justify-between md:items-center py-4">
      <!-- Logo -->
      <div class="flex items-center justify-between">
        <div class="text-xl font-bold text-gray-800">
          <img src="logo.svg" alt="Logo" class="h-8">
        </div>
        
        <!-- Botão de menu móvel -->
        <div class="md:hidden">
          <button type="button" class="text-gray-500 hover:text-gray-600">
            <svg class="h-6 w-6 fill-current" viewBox="0 0 24 24">
              <path d="M4 5h16a1 1 0 0 1 0 2H4a1 1 0 1 1 0-2zm0 6h16a1 1 0 0 1 0 2H4a1 1 0 0 1 0-2zm0 6h16a1 1 0 0 1 0 2H4a1 1 0 0 1 0-2z"></path>
            </svg>
          </button>
        </div>
      </div>
      
      <!-- Links de navegação (colapsáveis em mobile) -->
      <nav class="hidden md:flex items-center space-x-10">
        <a href="#" class="text-gray-800 hover:text-blue-600">Home</a>
        <a href="#" class="text-gray-600 hover:text-blue-600">Produtos</a>
        <a href="#" class="text-gray-600 hover:text-blue-600">Sobre</a>
        <a href="#" class="text-gray-600 hover:text-blue-600">Contato</a>
      </nav>
    </div>
  </div>
</header>
```

### 2. Cards Responsivos

```html
<div class="container mx-auto px-4 py-8">
  <h2 class="text-2xl md:text-3xl font-bold mb-6">Nossos Produtos</h2>
  
  <!-- Grid de cards responsivos -->
  <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 xl:grid-cols-4 gap-6">
    <!-- Card 1 -->
    <div class="bg-white rounded-lg shadow-md overflow-hidden">
      <img src="produto1.jpg" alt="Produto 1" class="w-full h-48 object-cover">
      <div class="p-4">
        <h3 class="text-lg font-semibold mb-2">Produto Premium</h3>
        <p class="text-gray-600 mb-4 line-clamp-2">Descrição do produto que pode ser muito longa e ocupar várias linhas.</p>
        <div class="flex justify-between items-center">
          <span class="text-blue-600 font-bold">R$ 199,90</span>
          <button class="bg-blue-600 text-white px-3 py-1 rounded hover:bg-blue-700">
            Comprar
          </button>
        </div>
      </div>
    </div>
    
    <!-- Repita para outros cards -->
  </div>
</div>
```

### 3. Layout de Página Completa

```html
<div class="min-h-screen flex flex-col">
  <!-- Cabeçalho -->
  <header class="bg-blue-600 text-white">
    <div class="container mx-auto px-4 py-3">
      <div class="flex justify-between items-center">
        <div class="text-xl font-bold">Meu Site</div>
        <nav class="hidden md:flex space-x-4">
          <a href="#" class="hover:text-blue-200">Home</a>
          <a href="#" class="hover:text-blue-200">Sobre</a>
          <a href="#" class="hover:text-blue-200">Serviços</a>
          <a href="#" class="hover:text-blue-200">Contato</a>
        </nav>
        <button class="md:hidden">Menu</button>
      </div>
    </div>
  </header>

  <!-- Conteúdo principal -->
  <main class="flex-grow">
    <!-- Hero Section -->
    <section class="bg-gray-100 py-12 md:py-20">
      <div class="container mx-auto px-4">
        <div class="flex flex-col md:flex-row items-center">
          <div class="md:w-1/2 mb-8 md:mb-0 md:pr-8">
            <h1 class="text-3xl sm:text-4xl md:text-5xl font-bold mb-4">
              Bem-vindo ao nosso site
            </h1>
            <p class="text-lg text-gray-600 mb-6">
              Uma descrição interessante para envolver seus visitantes.
            </p>
            <button class="bg-blue-600 text-white px-6 py-3 rounded-lg hover:bg-blue-700">
              Comece Agora
            </button>
          </div>
          <div class="md:w-1/2">
            <img src="hero-image.jpg" alt="Hero Image" class="rounded-lg shadow-lg">
          </div>
        </div>
      </div>
    </section>

    <!-- Seção de recursos -->
    <section class="py-12">
      <div class="container mx-auto px-4">
        <h2 class="text-2xl md:text-3xl font-bold text-center mb-12">Nossos Recursos</h2>
        
        <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
          <!-- Recurso 1 -->
          <div class="text-center">
            <div class="bg-blue-100 rounded-full p-4 inline-block mb-4">
              <!-- Ícone aqui -->
            </div>
            <h3 class="text-xl font-semibold mb-2">Recurso 1</h3>
            <p class="text-gray-600">Descrição do recurso 1.</p>
          </div>
          
          <!-- Recurso 2 -->
          <div class="text-center">
            <div class="bg-green-100 rounded-full p-4 inline-block mb-4">
              <!-- Ícone aqui -->
            </div>
            <h3 class="text-xl font-semibold mb-2">Recurso 2</h3>
            <p class="text-gray-600">Descrição do recurso 2.</p>
          </div>
          
          <!-- Recurso 3 -->
          <div class="text-center">
            <div class="bg-purple-100 rounded-full p-4 inline-block mb-4">
              <!-- Ícone aqui -->
            </div>
            <h3 class="text-xl font-semibold mb-2">Recurso 3</h3>
            <p class="text-gray-600">Descrição do recurso 3.</p>
          </div>
        </div>
      </div>
    </section>
  </main>

  <!-- Rodapé -->
  <footer class="bg-gray-800 text-white py-8">
    <div class="container mx-auto px-4">
      <div class="grid grid-cols-1 md:grid-cols-4 gap-8">
        <!-- Coluna 1 -->
        <div>
          <h4 class="text-lg font-semibold mb-4">Sobre Nós</h4>
          <p class="text-gray-400">Uma breve descrição da empresa.</p>
        </div>
        
        <!-- Coluna 2 -->
        <div>
          <h4 class="text-lg font-semibold mb-4">Links Rápidos</h4>
          <ul class="space-y-2 text-gray-400">
            <li><a href="#" class="hover:text-white">Home</a></li>
            <li><a href="#" class="hover:text-white">Sobre</a></li>
            <li><a href="#" class="hover:text-white">Serviços</a></li>
            <li><a href="#" class="hover:text-white">Contato</a></li>
          </ul>
        </div>
        
        <!-- Coluna 3 -->
        <div>
          <h4 class="text-lg font-semibold mb-4">Contato</h4>
          <ul class="space-y-2 text-gray-400">
            <li>contato@empresa.com</li>
            <li>(00) 1234-5678</li>
            <li>Rua Exemplo, 123</li>
          </ul>
        </div>
        
        <!-- Coluna 4 -->
        <div>
          <h4 class="text-lg font-semibold mb-4">Siga-nos</h4>
          <div class="flex space-x-4">
            <!-- Ícones de redes sociais aqui -->
          </div>
        </div>
      </div>
      
      <div class="border-t border-gray-700 mt-8 pt-6 text-center text-gray-400">
        <p>&copy; 2023 Minha Empresa. Todos os direitos reservados.</p>
      </div>
    </div>
  </footer>
</div>
```

## 🧪 Testes de Responsividade

Ao desenvolver com Tailwind CSS, teste seu layout em múltiplos dispositivos ou use as ferramentas de desenvolvimento do navegador:

1. Ferramentas de desenvolvimento do Chrome/Firefox
2. [Responsively App](https://responsively.app/)
3. [Sizzy](https://sizzy.co/)

## 🔗 Links Úteis

- [Documentação de Responsividade no Tailwind](https://tailwindcss.com/docs/responsive-design)
- [Exemplos de Componentes Responsivos](https://tailwindcomponents.com/)
- [Container Queries no Tailwind](https://tailwindcss.com/docs/container-queries)
- [Como testar sites responsivos](https://www.browserstack.com/guide/how-to-test-responsive-websites)

---

[⬅️ Voltar para o início](../README.md)

<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=06B6D4&height=120&section=footer"/> 