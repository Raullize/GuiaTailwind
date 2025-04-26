<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=06B6D4&height=120&section=header&fontSize=30&fontColor=fff&animation=twinkling&fontAlignY=35"/>

# 🎬 Animações e Transições no Tailwind CSS 🌟

O Tailwind CSS oferece um conjunto de classes utilitárias para adicionar animações e transições aos elementos HTML, permitindo criar interfaces dinâmicas e interativas sem escrever CSS personalizado.

## 🔄 Transições

As transições permitem que as mudanças de propriedades ocorram suavemente ao longo do tempo, em vez de instantaneamente.

### Habilitando Transições

Para adicionar uma transição, use a classe `transition`:

```html
<button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded transition">
  Passe o mouse para ver a transição
</button>
```

### Propriedades Específicas

Você pode especificar quais propriedades devem ser animadas:

```html
<button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded transition-colors">
  Apenas a cor faz transição
</button>

<div class="w-24 h-24 bg-blue-500 hover:w-48 transition-width">
  Apenas a largura faz transição
</div>

<!-- Outras opções -->
<div class="transition-all">Todas as propriedades</div>
<div class="transition-opacity">Apenas opacidade</div>
<div class="transition-transform">Apenas transformações</div>
<div class="transition-shadow">Apenas sombras</div>
<div class="transition-[margin]">Transição personalizada</div>
```

### Duração da Transição

Defina quanto tempo a transição deve levar:

```html
<div class="transition duration-150">150ms (rápida)</div>
<div class="transition duration-300">300ms (padrão)</div>
<div class="transition duration-500">500ms (média)</div>
<div class="transition duration-700">700ms</div>
<div class="transition duration-1000">1000ms (lenta)</div>
<div class="transition duration-[2000ms]">2000ms (personalizada)</div>
```

### Timing (Curva de Aceleração)

Controle como a transição progride ao longo do tempo:

```html
<div class="transition ease-linear">Linear</div>
<div class="transition ease-in">Aceleração no início</div>
<div class="transition ease-out">Desaceleração no final</div>
<div class="transition ease-in-out">Aceleração no início e desaceleração no final</div>
<div class="transition ease-[cubic-bezier(0.95,0.05,0.795,0.035)]">Curva personalizada</div>
```

### Delay

Adie o início da transição com:

```html
<div class="transition delay-150">Delay de 150ms</div>
<div class="transition delay-300">Delay de 300ms</div>
<div class="transition delay-500">Delay de 500ms</div>
<div class="transition delay-700">Delay de 700ms</div>
<div class="transition delay-1000">Delay de 1000ms</div>
```

### Combinando Propriedades

```html
<button class="bg-blue-500 hover:bg-blue-700 hover:scale-105 text-white font-bold py-2 px-4 rounded 
  transition-all duration-300 ease-in-out hover:shadow-lg transform">
  Botão com Transição Completa
</button>
```

## 🔄 Transformações

### Escala (Scale)

Aumentar ou diminuir elementos:

```html
<div class="scale-0">0% do tamanho original</div>
<div class="scale-50">50% do tamanho original</div>
<div class="scale-75">75% do tamanho original</div>
<div class="scale-90">90% do tamanho original</div>
<div class="scale-100">Tamanho original (100%)</div>
<div class="scale-105">105% do tamanho original</div>
<div class="scale-110">110% do tamanho original</div>
<div class="scale-125">125% do tamanho original</div>
<div class="scale-150">150% do tamanho original</div>

<!-- Escala individual em cada eixo -->
<div class="scale-x-50">50% da largura</div>
<div class="scale-y-50">50% da altura</div>
```

### Rotação (Rotate)

Gire elementos em graus:

```html
<div class="rotate-0">Sem rotação</div>
<div class="rotate-45">45 graus</div>
<div class="rotate-90">90 graus</div>
<div class="rotate-180">180 graus</div>
<div class="-rotate-45">-45 graus (anti-horário)</div>
<div class="rotate-[17deg]">17 graus (valor personalizado)</div>
```

### Translação (Movimento)

Mova elementos em diferentes direções:

```html
<div class="translate-x-0">Sem movimento horizontal</div>
<div class="translate-x-4">Move 1rem para direita</div>
<div class="-translate-x-4">Move 1rem para esquerda</div>

<div class="translate-y-0">Sem movimento vertical</div>
<div class="translate-y-4">Move 1rem para baixo</div>
<div class="-translate-y-4">Move 1rem para cima</div>

<div class="translate-x-1/4">Move 25% para direita</div>
<div class="translate-y-full">Move 100% para baixo</div>
<div class="translate-x-[55px]">Move 55px (valor personalizado)</div>
```

### Inclinação (Skew)

Incline elementos:

```html
<div class="skew-x-0">Sem inclinação horizontal</div>
<div class="skew-x-3">Inclinação horizontal 3 graus</div>
<div class="skew-y-6">Inclinação vertical 6 graus</div>
<div class="-skew-x-12">Inclinação horizontal -12 graus</div>
```

### Ponto de Origem

Define o ponto em torno do qual a transformação ocorre:

```html
<div class="origin-center">Centro (padrão)</div>
<div class="origin-top-left">Canto superior esquerdo</div>
<div class="origin-top-right">Canto superior direito</div>
<div class="origin-bottom">Centro inferior</div>
<div class="origin-left">Centro esquerdo</div>
```

### Combinando Transformações

```html
<div class="scale-110 rotate-6 translate-x-2 skew-y-3">
  Múltiplas transformações
</div>
```

## 🎭 Animações

O Tailwind possui algumas animações predefinidas e permite criar as suas próprias.

### Animações Padrão

```html
<div class="animate-spin">Girando em 360°</div>
<div class="animate-ping">Efeito de pulso</div>
<div class="animate-pulse">Pulso suave</div>
<div class="animate-bounce">Efeito de salto</div>
```

### Personalizando Animações

Você pode definir suas próprias animações no arquivo `tailwind.config.js`:

```javascript
// tailwind.config.js
module.exports = {
  theme: {
    extend: {
      keyframes: {
        wiggle: {
          '0%, 100%': { transform: 'rotate(-3deg)' },
          '50%': { transform: 'rotate(3deg)' },
        },
        fadeIn: {
          '0%': { opacity: 0 },
          '100%': { opacity: 1 },
        }
      },
      animation: {
        wiggle: 'wiggle 1s ease-in-out infinite',
        fadeIn: 'fadeIn 1s ease-in forwards',
      }
    },
  },
}
```

Uso:

```html
<div class="animate-wiggle">Animação personalizada de balanço</div>
<div class="animate-fadeIn">Fade in personalizado</div>
```

### Duração da Animação

Controle o tempo total de uma animação:

```html
<div class="animate-bounce animation-duration-1000">1 segundo</div>
<div class="animate-spin animation-duration-[2000ms]">2 segundos</div>
```

### Iteração da Animação 

Controle quantas vezes a animação é executada:

```html
<div class="animate-pulse animation-iteration-1">Uma vez</div>
<div class="animate-bounce animation-iteration-infinite">Infinitamente</div>
```

### Delay da Animação

Atrase o início da animação:

```html
<div class="animate-ping animation-delay-500">Delay de 500ms</div>
<div class="animate-bounce animation-delay-1000">Delay de 1 segundo</div>
<div class="animate-spin animation-delay-[2000ms]">Delay de 2 segundos</div>
```

### Direção da Animação

```html
<div class="animate-bounce animation-direction-normal">Normal</div>
<div class="animate-bounce animation-direction-reverse">Reversa</div>
<div class="animate-bounce animation-direction-alternate">Alternada</div>
```

### Estado da Animação

```html
<div class="animate-spin animation-running">Executando (padrão)</div>
<div class="animate-spin animation-paused">Pausada</div>
```

### Modo de Preenchimento

```html
<div class="animate-fadeIn animation-fill-mode-forwards">
  Mantém o estado final após a animação
</div>
<div class="animate-fadeIn animation-fill-mode-backwards">
  Aplica o estado inicial antes de começar
</div>
<div class="animate-fadeIn animation-fill-mode-both">
  Combina forwards e backwards
</div>
```

## 🧠 Usando Eventos para Triggering

### Hover

```html
<button class="bg-blue-500 text-white py-2 px-4 rounded 
  hover:bg-blue-700 hover:scale-105 transition duration-300">
  Efeito no Hover
</button>
```

### Focus

```html
<input type="text" class="border border-gray-300 rounded py-2 px-4 
  focus:border-blue-500 focus:ring-2 focus:ring-blue-200 transition duration-200">
```

### Active

```html
<button class="bg-green-500 text-white py-2 px-4 rounded 
  transform transition duration-150 active:scale-95">
  Pressione para efeito
</button>
```

### Grupo-Hover

```html
<div class="group p-6 bg-white rounded-lg shadow-md hover:shadow-xl transition-shadow duration-300">
  <h3 class="text-lg font-semibold transition-colors group-hover:text-blue-500">Título do Card</h3>
  <p class="text-gray-600 opacity-75 transition-opacity group-hover:opacity-100">
    Descrição que fica mais visível no hover do grupo.
  </p>
  <div class="mt-4 transform translate-y-1 opacity-0 transition duration-300 group-hover:translate-y-0 group-hover:opacity-100">
    Conteúdo oculto que aparece gradualmente.
  </div>
</div>
```

## 🎯 Exemplos Práticos

### 1. Botão com Efeito de Clique

```html
<button class="bg-blue-500 hover:bg-blue-600 text-white font-bold py-2 px-6 rounded 
  transform transition duration-150 ease-in-out active:scale-95 hover:shadow-lg">
  Clique em Mim
</button>
```

### 2. Card com Hover Effect

```html
<div class="max-w-sm mx-auto bg-white rounded-xl shadow-md overflow-hidden transform transition duration-500 hover:scale-105 hover:shadow-xl">
  <div class="md:flex">
    <div class="md:shrink-0">
      <img class="h-48 w-full object-cover md:w-48" src="https://source.unsplash.com/random/300x200" alt="Imagem">
    </div>
    <div class="p-8">
      <div class="uppercase tracking-wide text-sm text-indigo-500 font-semibold">Categoria</div>
      <a href="#" class="block mt-1 text-lg leading-tight font-medium text-black hover:text-indigo-500 transition">Título do Card</a>
      <p class="mt-2 text-slate-500">Conteúdo do card com descrição.</p>
    </div>
  </div>
</div>
```

### 3. Menu de Navegação com Transição

```html
<nav class="bg-white shadow">
  <div class="max-w-7xl mx-auto px-4">
    <div class="flex justify-between h-16">
      <div class="flex">
        <div class="flex-shrink-0 flex items-center">
          <img class="block h-8 w-auto" src="logo.svg" alt="Logo">
        </div>
        <div class="hidden sm:ml-6 sm:flex">
          <a href="#" class="inline-flex items-center px-1 pt-1 border-b-2 border-indigo-500 text-sm font-medium text-gray-900">
            Home
          </a>
          <a href="#" class="inline-flex items-center px-1 pt-1 border-b-2 border-transparent text-sm font-medium text-gray-500 hover:text-gray-700 hover:border-gray-300 transition duration-150">
            Recursos
          </a>
          <a href="#" class="inline-flex items-center px-1 pt-1 border-b-2 border-transparent text-sm font-medium text-gray-500 hover:text-gray-700 hover:border-gray-300 transition duration-150">
            Sobre
          </a>
        </div>
      </div>
    </div>
  </div>
</nav>
```

### 4. Dropdown com Animação

```html
<div class="relative inline-block text-left">
  <div>
    <button id="dropdown-btn" class="inline-flex justify-center w-full rounded-md border border-gray-300 shadow-sm px-4 py-2 bg-white text-sm font-medium text-gray-700 hover:bg-gray-50 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-indigo-500">
      Opções
      <svg class="-mr-1 ml-2 h-5 w-5" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20" fill="currentColor">
        <path fill-rule="evenodd" d="M5.293 7.293a1 1 0 011.414 0L10 10.586l3.293-3.293a1 1 0 111.414 1.414l-4 4a1 1 0 01-1.414 0l-4-4a1 1 0 010-1.414z" clip-rule="evenodd" />
      </svg>
    </button>
  </div>

  <div id="dropdown-menu" class="hidden origin-top-right absolute right-0 mt-2 w-56 rounded-md shadow-lg bg-white ring-1 ring-black ring-opacity-5 divide-y divide-gray-100 transform opacity-0 scale-95 transition-all duration-200 ease-out">
    <div class="py-1">
      <a href="#" class="block px-4 py-2 text-sm text-gray-700 hover:bg-gray-100 transition">Editar</a>
      <a href="#" class="block px-4 py-2 text-sm text-gray-700 hover:bg-gray-100 transition">Duplicar</a>
    </div>
    <div class="py-1">
      <a href="#" class="block px-4 py-2 text-sm text-red-600 hover:bg-gray-100 transition">Excluir</a>
    </div>
  </div>
</div>

<script>
  const btn = document.getElementById('dropdown-btn');
  const menu = document.getElementById('dropdown-menu');
  
  btn.addEventListener('click', () => {
    const isExpanded = menu.classList.contains('opacity-100');
    
    if (!isExpanded) {
      menu.classList.remove('hidden');
      setTimeout(() => {
        menu.classList.remove('opacity-0', 'scale-95');
        menu.classList.add('opacity-100', 'scale-100');
      }, 10);
    } else {
      menu.classList.remove('opacity-100', 'scale-100');
      menu.classList.add('opacity-0', 'scale-95');
      setTimeout(() => {
        menu.classList.add('hidden');
      }, 200);
    }
  });
</script>
```

### 5. Loading Spinner

```html
<div class="flex items-center justify-center">
  <div class="animate-spin rounded-full h-12 w-12 border-t-2 border-b-2 border-blue-500"></div>
</div>
```

### 6. Notificação Toast

```html
<div id="toast" class="fixed top-4 right-4 px-4 py-2 bg-green-500 text-white rounded shadow-lg transform translate-x-full opacity-0 transition-all duration-500 ease-in-out">
  Operação realizada com sucesso!
</div>

<button onclick="showToast()" class="mt-4 px-4 py-2 bg-blue-500 text-white rounded hover:bg-blue-600 transition">
  Mostrar Notificação
</button>

<script>
  function showToast() {
    const toast = document.getElementById('toast');
    
    // Mostrar
    toast.classList.remove('translate-x-full', 'opacity-0');
    toast.classList.add('translate-x-0', 'opacity-100');
    
    // Esconder após 3 segundos
    setTimeout(() => {
      toast.classList.remove('translate-x-0', 'opacity-100');
      toast.classList.add('translate-x-full', 'opacity-0');
    }, 3000);
  }
</script>
```

### 7. Fade-in de Imagem

```html
<div class="bg-gray-200 animate-pulse h-64 w-full rounded-lg overflow-hidden relative">
  <img 
    src="https://source.unsplash.com/random/800x600" 
    alt="Imagem" 
    class="absolute inset-0 h-full w-full object-cover opacity-0 transition-opacity duration-1000 ease-in-out"
    onload="this.classList.remove('opacity-0')"
  >
</div>
```

### 8. Accordeon (Sanfona)

```html
<div class="w-full max-w-md mx-auto">
  <div class="border rounded-md overflow-hidden">
    <div class="border-b last:border-b-0">
      <button id="acc-btn-1" class="flex justify-between items-center w-full px-4 py-3 text-left font-medium">
        <span>Seção 1</span>
        <svg id="acc-arrow-1" class="w-5 h-5 transform transition-transform duration-200" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"></path>
        </svg>
      </button>
      <div id="acc-content-1" class="max-h-0 overflow-hidden transition-all duration-300 ease-in-out">
        <div class="p-4 border-t">
          Conteúdo da seção 1. Este é um texto de exemplo para demonstrar o accordeon.
        </div>
      </div>
    </div>
    
    <!-- Seção 2 -->
    <div class="border-b last:border-b-0">
      <button id="acc-btn-2" class="flex justify-between items-center w-full px-4 py-3 text-left font-medium">
        <span>Seção 2</span>
        <svg id="acc-arrow-2" class="w-5 h-5 transform transition-transform duration-200" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"></path>
        </svg>
      </button>
      <div id="acc-content-2" class="max-h-0 overflow-hidden transition-all duration-300 ease-in-out">
        <div class="p-4 border-t">
          Conteúdo da seção 2. Este é um texto de exemplo para demonstrar o accordeon.
        </div>
      </div>
    </div>
  </div>
</div>

<script>
  // Controle de accordeon
  function setupAccordeon(btnId, contentId, arrowId) {
    const btn = document.getElementById(btnId);
    const content = document.getElementById(contentId);
    const arrow = document.getElementById(arrowId);
    
    btn.addEventListener('click', () => {
      const isOpen = content.classList.contains('max-h-screen');
      
      if (!isOpen) {
        content.classList.remove('max-h-0');
        content.classList.add('max-h-screen');
        arrow.classList.add('rotate-180');
      } else {
        content.classList.remove('max-h-screen');
        content.classList.add('max-h-0');
        arrow.classList.remove('rotate-180');
      }
    });
  }
  
  // Configurar seções
  setupAccordeon('acc-btn-1', 'acc-content-1', 'acc-arrow-1');
  setupAccordeon('acc-btn-2', 'acc-content-2', 'acc-arrow-2');
</script>
```

## 🚫 Desativando Animações

Para usuários que preferem interfaces sem animação, você pode respeitar a configuração `prefers-reduced-motion`:

```html
<div class="animate-bounce motion-reduce:animate-none">
  Este elemento só vai pular se o usuário não preferir redução de movimento
</div>

<button class="transition hover:scale-105 motion-reduce:transform-none">
  Botão respeita prefers-reduced-motion
</button>
```

## 🎯 Melhores Práticas

1. **Use transições com moderação**: Muitas animações podem deixar a interface lenta e distrair os usuários.

2. **Mantenha as animações rápidas**: Para interações comuns, mantenha as animações curtas (150-300ms).

3. **Priorize desempenho**: Anime apenas propriedades que o navegador pode otimizar (transform e opacity).

4. **Considere a acessibilidade**: Forneça alternativas para usuários que preferem reduzir animações.

5. **Combine com estados interativos**: As animações são mais eficazes quando fornecem feedback para interações do usuário.

## 🔗 Links Úteis

- [Documentação de transições no Tailwind](https://tailwindcss.com/docs/transition-property)
- [Documentação de transformações no Tailwind](https://tailwindcss.com/docs/transform)
- [Documentação de animações no Tailwind](https://tailwindcss.com/docs/animation)
- [Exemplos de animações CSS](https://animate.style/) (para inspiração)
- [Guia de performance CSS](https://web.dev/animations-guide/)

---

[⬅️ Voltar para o início](../README.md)

<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=06B6D4&height=120&section=footer"/> 