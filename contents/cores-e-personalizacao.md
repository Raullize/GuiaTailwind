<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=06B6D4&height=120&section=header&fontSize=30&fontColor=fff&animation=twinkling&fontAlignY=35"/>

# Cores e Personalização no Tailwind CSS

O Tailwind CSS oferece um sistema de cores rico e altamente personalizável. Esta seção explora como usar e personalizar as cores e outros aspectos visuais do seu projeto.

## Sistema de Cores Padrão

O Tailwind vem com uma paleta de cores predefinida, cada uma com diferentes tons de intensidade (do 50 ao 900).

### Paletas Disponíveis

- `slate`: Tons neutros com um toque azulado
- `gray`: Cinzas puros
- `zinc`: Cinzas neutros
- `neutral`: Cinzas verdadeiramente neutros
- `stone`: Cinzas com um toque marrom
- `red`: Vermelhos
- `orange`: Laranjas
- `amber`: Âmbar
- `yellow`: Amarelos
- `lime`: Verde-limão
- `green`: Verdes
- `emerald`: Verde-esmeralda
- `teal`: Verde-azulado
- `cyan`: Ciano
- `sky`: Azul-céu
- `blue`: Azuis
- `indigo`: Índigo
- `violet`: Violeta
- `purple`: Roxos
- `fuchsia`: Fúcsia
- `pink`: Rosa
- `rose`: Rosa-avermelhado

Além dessas, também existem:
- `black`: Preto
- `white`: Branco
- `transparent`: Transparente
- `current`: Cor atual

## Como Usar Cores

### Texto

```html
<p class="text-blue-500">Texto em azul médio</p>
<p class="text-red-700">Texto em vermelho escuro</p>
<p class="text-green-300">Texto em verde claro</p>
<p class="text-gray-900">Texto quase preto</p>
```

### Fundos

```html
<div class="bg-yellow-200">Fundo amarelo claro</div>
<div class="bg-purple-600">Fundo roxo médio</div>
<div class="bg-gradient-to-r from-cyan-500 to-blue-500">Fundo gradiente</div>
```

### Bordas

```html
<div class="border-2 border-pink-500">Borda rosa</div>
<div class="border-t-4 border-indigo-700">Borda superior índigo</div>
```

### Preenchimento e Traçado (SVG)

```html
<svg class="fill-blue-500 stroke-blue-700">...</svg>
```

### Transparência (Opacidade)

O Tailwind permite adicionar transparência a cores:

```html
<div class="bg-blue-500 bg-opacity-50">Fundo azul 50% transparente</div>
<p class="text-black text-opacity-70">Texto preto 70% opaco</p>
```

Na versão 3+, também é possível usar a notação de barra:

```html
<div class="bg-blue-500/50">Fundo azul 50% transparente</div>
<p class="text-black/70">Texto preto 70% opaco</p>
```

## Personalizando Cores

### No arquivo tailwind.config.js

Você pode estender ou substituir as cores padrão:

```javascript
// tailwind.config.js
module.exports = {
  theme: {
    // Substituir completamente (remove cores padrão)
    colors: {
      'azul-marca': '#1E40AF',
      'verde-marca': '#10B981',
      'cinza-claro': '#F3F4F6',
    },
    // OU estender (mantém cores padrão)
    extend: {
      colors: {
        'azul-marca': '#1E40AF',
        'verde-marca': '#10B981',
        'cinza-claro': '#F3F4F6',
      }
    }
  }
}
```

### Definindo tons

Você pode definir uma cor com vários tons:

```javascript
module.exports = {
  theme: {
    extend: {
      colors: {
        'marca': {
          50: '#f0f9ff',
          100: '#e0f2fe',
          200: '#bae6fd',
          300: '#7dd3fc',
          400: '#38bdf8',
          500: '#0ea5e9',
          600: '#0284c7',
          700: '#0369a1',
          800: '#075985',
          900: '#0c4a6e',
        }
      }
    }
  }
}
```

Uso:

```html
<div class="bg-marca-600">Usando cor personalizada</div>
<p class="text-marca-300">Texto em cor personalizada clara</p>
```

## Modo Escuro

O Tailwind simplifica a implementação do modo escuro:

```javascript
// tailwind.config.js
module.exports = {
  darkMode: 'class', // ou 'media'
}
```

- `'class'`: Ativa o modo escuro baseado em classes (ex: adicionar `.dark` ao elemento `html`)
- `'media'`: Ativa o modo escuro baseado na preferência do sistema (via `prefers-color-scheme`)

Usando o modo escuro:

```html
<div class="bg-white dark:bg-gray-800 text-black dark:text-white">
  Conteúdo que se adapta ao modo escuro
</div>
```

## Função Theme()

Dentro do seu CSS personalizado, você pode acessar os valores de tema do Tailwind:

```css
.elemento-personalizado {
  background-color: theme('colors.blue.500');
  padding: theme('spacing.4');
  border-radius: theme('borderRadius.lg');
}
```

## CSS Personalizado em Camadas

O Tailwind define três camadas onde você pode injetar CSS:

```css
@layer base {
  /* Estilos base, como resets, elementos HTML, etc. */
  h1 {
    @apply text-2xl font-bold;
  }
}

@layer components {
  /* Componentes reutilizáveis */
  .btn-primary {
    @apply px-4 py-2 bg-blue-500 text-white rounded;
  }
}

@layer utilities {
  /* Utilitários personalizados */
  .shadow-custom {
    box-shadow: 0 0 15px rgba(0, 0, 0, 0.2);
  }
}
```

## Diretiva Apply

A diretiva `@apply` permite compor classes utilitárias em estilos CSS:

```css
.btn {
  @apply py-2 px-4 rounded;
}

.btn-blue {
  @apply bg-blue-500 text-white hover:bg-blue-700;
}
```

Agora você pode simplesmente usar:

```html
<button class="btn btn-blue">Botão Azul</button>
```

## Criando Plugins

Para funcionalidades mais complexas, você pode criar plugins:

```javascript
// tailwind.config.js
const plugin = require('tailwindcss/plugin')

module.exports = {
  plugins: [
    plugin(function({ addUtilities, theme }) {
      const newUtilities = {
        '.text-shadow-sm': {
          textShadow: '0 1px 2px rgba(0, 0, 0, 0.1)',
        },
        '.text-shadow': {
          textShadow: '0 2px 4px rgba(0, 0, 0, 0.1)',
        },
        '.text-shadow-lg': {
          textShadow: '0 4px 8px rgba(0, 0, 0, 0.1)',
        },
      }
      addUtilities(newUtilities)
    })
  ]
}
```

## Gradientes

O Tailwind inclui suporte para gradientes:

```html
<!-- Gradiente linear horizontal -->
<div class="bg-gradient-to-r from-cyan-500 to-blue-500">
  Gradiente de ciano para azul
</div>

<!-- Com ponto intermediário -->
<div class="bg-gradient-to-r from-purple-500 via-pink-500 to-red-500">
  Gradiente com ponto intermediário
</div>

<!-- Direções -->
<div class="bg-gradient-to-t">De baixo para cima</div>
<div class="bg-gradient-to-tr">Para o canto superior direito</div>
<div class="bg-gradient-to-r">Da esquerda para a direita</div>
<div class="bg-gradient-to-br">Para o canto inferior direito</div>
<div class="bg-gradient-to-b">De cima para baixo</div>
<div class="bg-gradient-to-bl">Para o canto inferior esquerdo</div>
<div class="bg-gradient-to-l">Da direita para a esquerda</div>
<div class="bg-gradient-to-tl">Para o canto superior esquerdo</div>
```

## Cores Arbitrárias

O Tailwind permite usar valores de cores arbitrários:

```html
<div class="bg-[#1E40AF]">Azul personalizado com notação hexadecimal</div>
<div class="text-[rgb(30,64,175)]">Azul personalizado com notação RGB</div>
<div class="border-[hsl(221,83%,53%)]">Azul personalizado com notação HSL</div>
```

## Esquemas de Cores Personalizados

Uma estratégia para criar um esquema de cores consistente:

```javascript
// tailwind.config.js
module.exports = {
  theme: {
    extend: {
      colors: {
        primary: {
          50: '#f0f9ff',
          100: '#e0f2fe',
          // ... outros tons
          600: '#0284c7', // cor principal
          // ... outros tons
          900: '#0c4a6e',
        },
        secondary: {
          // tons da cor secundária
        },
        accent: {
          // tons da cor de destaque
        },
        // Cores de estado
        success: '#10B981',
        warning: '#F59E0B',
        error: '#EF4444',
        info: '#3B82F6',
      }
    }
  }
}
```

## Exemplos Práticos

### 1. Botão principal com hover e focus

```html
<button class="
  bg-primary-600 hover:bg-primary-700 focus:ring-2 focus:ring-primary-400 focus:ring-opacity-50
  text-white font-semibold
  py-2 px-4
  rounded-lg
  transition duration-150 ease-in-out
">
  Botão Principal
</button>
```

### 2. Card com tema escuro

```html
<div class="
  bg-white dark:bg-gray-800
  shadow-md rounded-lg p-6
  border border-gray-200 dark:border-gray-700
">
  <h2 class="text-gray-900 dark:text-white text-xl font-semibold">Título do Card</h2>
  <p class="text-gray-600 dark:text-gray-300 mt-2">Conteúdo do card com suporte a tema escuro.</p>
</div>
```

### 3. Badge de notificação

```html
<span class="inline-flex items-center justify-center px-2 py-1 text-xs font-bold leading-none text-red-100 bg-red-600 rounded-full">
  42
</span>
```

## Links Úteis

- [Documentação de cores](https://tailwindcss.com/docs/customizing-colors)
- [Guia de personalização](https://tailwindcss.com/docs/theme)
- [Modo escuro](https://tailwindcss.com/docs/dark-mode)
- [Paleta de cores Tailwind](https://tailwindcss.com/docs/customizing-colors#color-palette-reference)

---

[⬅️ Voltar para o início](../README.md)

<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=06B6D4&height=120&section=footer"/>