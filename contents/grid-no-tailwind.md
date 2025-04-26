<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=06B6D4&height=120&section=header&fontSize=30&fontColor=fff&animation=twinkling&fontAlignY=35"/>

# 📊 Grid no Tailwind CSS 🏗️

O CSS Grid é um poderoso sistema de layout bidimensional que o Tailwind CSS integra perfeitamente através de classes utilitárias intuitivas. Essa tecnologia permite criar layouts complexos com controle preciso tanto em linhas quanto em colunas.

## 📋 Habilitando o Grid

Para usar o Grid, primeiro defina um elemento como um container grid:

```html
<div class="grid">
  <!-- Itens do grid aqui -->
</div>

<!-- Para display: inline-grid -->
<div class="inline-grid">
  <!-- Itens do grid aqui -->
</div>
```

## 🏗️ Definindo Colunas (Grid Template Columns)

### Número de colunas predefinido

O Tailwind oferece classes para criar de 1 a 12 colunas de tamanhos iguais:

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
<div class="grid grid-cols-none">Sem colunas explícitas</div>
```

### Colunas com tamanhos personalizados

Para tamanhos específicos, você pode usar valores arbitrários:

```html
<!-- Colunas com larguras específicas -->
<div class="grid grid-cols-[200px_1fr_2fr]">
  <div>200px</div>
  <div>1fr (flexível)</div>
  <div>2fr (2x flexível)</div>
</div>

<!-- Colunas repetidas com tamanhos específicos -->
<div class="grid grid-cols-[repeat(2,_200px)_1fr]">
  <div>200px</div>
  <div>200px</div>
  <div>1fr</div>
</div>
```

## 🏢 Definindo Linhas (Grid Template Rows)

Similar às colunas, você pode definir o número de linhas explícitas:

```html
<div class="grid grid-rows-1">1 linha</div>
<div class="grid grid-rows-2">2 linhas</div>
<div class="grid grid-rows-3">3 linhas</div>
<div class="grid grid-rows-4">4 linhas</div>
<div class="grid grid-rows-5">5 linhas</div>
<div class="grid grid-rows-6">6 linhas</div>
<div class="grid grid-rows-none">Sem linhas explícitas</div>
```

### Linhas com alturas personalizadas

```html
<!-- Alturas específicas para linhas -->
<div class="grid grid-rows-[100px_200px_auto]">
  <div>100px</div>
  <div>200px</div>
  <div>Auto</div>
</div>
```

## 📏 Posicionamento e Dimensionamento de Itens

### Span de Coluna (Column Span)

Controle quantas colunas um item deve ocupar:

```html
<div class="grid grid-cols-6">
  <div class="col-span-1">Ocupa 1 coluna</div>
  <div class="col-span-2">Ocupa 2 colunas</div>
  <div class="col-span-3">Ocupa 3 colunas</div>
  
  <!-- Também disponível: col-span-4, col-span-5, col-span-6... até col-span-12 -->
  
  <!-- Ocupa todas as colunas disponíveis -->
  <div class="col-span-full">Ocupa todas as colunas</div>
</div>
```

### Span de Linha (Row Span)

Controle quantas linhas um item deve ocupar:

```html
<div class="grid grid-rows-6">
  <div class="row-span-1">Ocupa 1 linha</div>
  <div class="row-span-2">Ocupa 2 linhas</div>
  <div class="row-span-3">Ocupa 3 linhas</div>
  
  <!-- Também disponível: row-span-4, row-span-5, row-span-6 -->
  
  <!-- Ocupa todas as linhas disponíveis -->
  <div class="row-span-full">Ocupa todas as linhas</div>
</div>
```

### Posicionamento Específico

Você pode posicionar itens em posições específicas da grade:

```html
<div class="grid grid-cols-3 grid-rows-3">
  <!-- Posicionamento de coluna (linha inicial / linha final) -->
  <div class="col-start-1 col-end-3">Da coluna 1 até a coluna 3</div>
  <div class="col-start-2 col-end-4">Da coluna 2 até a coluna 4</div>
  
  <!-- Posicionamento automático -->
  <div class="col-start-auto">Posicionamento automático</div>
  <div class="col-end-auto">Posicionamento automático</div>
  
  <!-- Posicionamento de linha (linha inicial / linha final) -->
  <div class="row-start-1 row-end-3">Da linha 1 até a linha 3</div>
  <div class="row-start-2 row-end-4">Da linha 2 até a linha 4</div>
  
  <!-- Combinando posicionamento de linha e coluna -->
  <div class="col-start-1 col-end-2 row-start-1 row-end-2">
    Célula específica
  </div>
</div>
```

## 📐 Espaçamento entre Itens (Gap)

Controle o espaçamento entre linhas e colunas:

```html
<!-- Espaçamento igual em todas as direções -->
<div class="grid grid-cols-3 gap-4">
  <!-- Itens com 1rem (16px) de espaço entre eles -->
</div>

<!-- Espaçamento apenas entre colunas -->
<div class="grid grid-cols-3 gap-x-4">
  <!-- Itens com 1rem de espaço horizontal -->
</div>

<!-- Espaçamento apenas entre linhas -->
<div class="grid grid-cols-3 gap-y-6">
  <!-- Itens com 1.5rem de espaço vertical -->
</div>

<!-- Espaçamentos diferentes -->
<div class="grid grid-cols-3 gap-x-4 gap-y-8">
  <!-- 1rem horizontal, 2rem vertical -->
</div>
```

## 🔄 Fluxo do Grid (Grid Auto Flow)

Determine como os itens são automaticamente posicionados na grade:

```html
<!-- Itens fluem por linha (padrão) -->
<div class="grid grid-flow-row">
  <!-- Itens -->
</div>

<!-- Itens fluem por coluna -->
<div class="grid grid-flow-col">
  <!-- Itens -->
</div>

<!-- Fluxo denso (tenta preencher buracos) -->
<div class="grid grid-flow-row-dense">
  <!-- Itens -->
</div>

<div class="grid grid-flow-col-dense">
  <!-- Itens -->
</div>
```

## 🌟 Auto-Columns e Auto-Rows

Defina o tamanho padrão de colunas e linhas criadas implicitamente:

```html
<!-- Colunas automáticas -->
<div class="grid auto-cols-auto">Tamanho automático</div>
<div class="grid auto-cols-min">Tamanho mínimo</div>
<div class="grid auto-cols-max">Tamanho máximo</div>
<div class="grid auto-cols-fr">Tamanho fracionário</div>

<!-- Linhas automáticas -->
<div class="grid auto-rows-auto">Tamanho automático</div>
<div class="grid auto-rows-min">Tamanho mínimo</div>
<div class="grid auto-rows-max">Tamanho máximo</div>
<div class="grid auto-rows-fr">Tamanho fracionário</div>
```

Para tamanhos personalizados:

```html
<div class="grid auto-cols-[200px]">Colunas automáticas de 200px</div>
<div class="grid auto-rows-[minmax(100px,_auto)]">Linhas automáticas mínimo 100px</div>
```

## 📱 Grid Responsivo

Adapte seu layout de grade para diferentes tamanhos de tela:

```html
<!-- Diferentes números de colunas dependendo do tamanho da tela -->
<div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 xl:grid-cols-6">
  <!-- Itens aqui -->
</div>

<!-- Posicionamento responsivo -->
<div class="grid grid-cols-6">
  <div class="col-span-6 md:col-span-4 lg:col-span-2">
    Ocupa larguras diferentes em tamanhos diferentes de tela
  </div>
</div>

<!-- Gaps responsivos -->
<div class="grid grid-cols-3 gap-2 md:gap-4 lg:gap-6">
  <!-- Espaçamento crescente em telas maiores -->
</div>
```

## 🎯 Alinhamento de Itens e Conteúdo

### Justify Items (alinhamento horizontal de todos os itens)

```html
<div class="grid justify-items-start">Itens alinhados ao início</div>
<div class="grid justify-items-end">Itens alinhados ao final</div>
<div class="grid justify-items-center">Itens centralizados</div>
<div class="grid justify-items-stretch">Itens esticados (padrão)</div>
```

### Align Items (alinhamento vertical de todos os itens)

```html
<div class="grid h-48 align-items-start">Itens alinhados ao topo</div>
<div class="grid h-48 align-items-end">Itens alinhados à base</div>
<div class="grid h-48 align-items-center">Itens centralizados</div>
<div class="grid h-48 align-items-stretch">Itens esticados (padrão)</div>
```

### Place Items (atalho para align e justify items)

```html
<div class="grid place-items-center h-48">Itens centralizados em ambos os eixos</div>
<div class="grid place-items-start h-48">Itens alinhados ao início em ambos os eixos</div>
<div class="grid place-items-end h-48">Itens alinhados ao final em ambos os eixos</div>
```

### Justify Content (alinhamento horizontal da grade inteira)

```html
<div class="grid justify-start">Grade alinhada ao início</div>
<div class="grid justify-end">Grade alinhada ao final</div>
<div class="grid justify-center">Grade centralizada</div>
<div class="grid justify-between">Espaço entre os itens</div>
<div class="grid justify-around">Espaço ao redor dos itens</div>
<div class="grid justify-evenly">Espaço uniforme</div>
```

### Align Content (alinhamento vertical da grade inteira)

```html
<div class="grid h-48 content-start">Grade alinhada ao topo</div>
<div class="grid h-48 content-end">Grade alinhada à base</div>
<div class="grid h-48 content-center">Grade centralizada</div>
<div class="grid h-48 content-between">Espaço entre as linhas</div>
<div class="grid h-48 content-around">Espaço ao redor das linhas</div>
<div class="grid h-48 content-evenly">Espaço uniforme entre linhas</div>
```

### Place Content (atalho para align e justify content)

```html
<div class="grid h-48 place-content-center">Grade centralizada em ambos os eixos</div>
<div class="grid h-48 place-content-start">Grade alinhada ao início em ambos os eixos</div>
<div class="grid h-48 place-content-end">Grade alinhada ao final em ambos os eixos</div>
```

### Alinhamento Individual (Self)

Você pode sobrescrever o alinhamento para itens específicos:

```html
<div class="grid justify-items-center">
  <div>Centralizado (padrão)</div>
  <div class="justify-self-start">Alinhado ao início</div>
  <div class="justify-self-end">Alinhado ao final</div>
  <div class="justify-self-stretch">Esticado</div>
  <div class="justify-self-auto">Auto</div>
</div>

<div class="grid h-48 align-items-center">
  <div>Centralizado (padrão)</div>
  <div class="self-start">Alinhado ao topo</div>
  <div class="self-end">Alinhado à base</div>
  <div class="self-stretch">Esticado</div>
  <div class="self-auto">Auto</div>
</div>

<div class="grid h-48 place-items-center">
  <div>Centralizado (padrão)</div>
  <div class="place-self-start">Alinhado ao início em ambos os eixos</div>
  <div class="place-self-end">Alinhado ao final em ambos os eixos</div>
  <div class="place-self-stretch">Esticado em ambos os eixos</div>
  <div class="place-self-auto">Auto em ambos os eixos</div>
</div>
```

## 🛠️ Exemplos Práticos

### 1. Layout de Galeria Responsiva

```html
<div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-4">
  <div class="bg-blue-100 p-4 rounded-lg shadow">Item 1</div>
  <div class="bg-blue-100 p-4 rounded-lg shadow">Item 2</div>
  <div class="bg-blue-100 p-4 rounded-lg shadow">Item 3</div>
  <div class="bg-blue-100 p-4 rounded-lg shadow">Item 4</div>
  <div class="bg-blue-100 p-4 rounded-lg shadow">Item 5</div>
  <div class="bg-blue-100 p-4 rounded-lg shadow">Item 6</div>
  <div class="bg-blue-100 p-4 rounded-lg shadow">Item 7</div>
  <div class="bg-blue-100 p-4 rounded-lg shadow">Item 8</div>
</div>
```

### 2. Layout de Dashboard

```html
<div class="grid grid-cols-12 gap-4">
  <!-- Cabeçalho que ocupa a largura completa -->
  <header class="col-span-12 bg-blue-600 text-white p-4 rounded-lg">
    Cabeçalho do Dashboard
  </header>
  
  <!-- Sidebar -->
  <aside class="col-span-12 md:col-span-3 bg-gray-100 p-4 rounded-lg">
    Menu de Navegação
    <nav class="mt-4 space-y-2">
      <a href="#" class="block p-2 bg-blue-500 text-white rounded">Dashboard</a>
      <a href="#" class="block p-2 hover:bg-gray-200 rounded">Relatórios</a>
      <a href="#" class="block p-2 hover:bg-gray-200 rounded">Usuários</a>
      <a href="#" class="block p-2 hover:bg-gray-200 rounded">Configurações</a>
    </nav>
  </aside>
  
  <!-- Conteúdo principal -->
  <main class="col-span-12 md:col-span-9 bg-white p-4 rounded-lg">
    <h1 class="text-xl font-bold mb-4">Painel Principal</h1>
    
    <!-- Cards de estatísticas em grid aninhado -->
    <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-4 mb-6">
      <div class="bg-blue-50 p-4 rounded-lg shadow">
        <h3 class="font-bold">Usuários</h3>
        <p class="text-2xl">1,245</p>
      </div>
      <div class="bg-green-50 p-4 rounded-lg shadow">
        <h3 class="font-bold">Receita</h3>
        <p class="text-2xl">$9,452</p>
      </div>
      <div class="bg-purple-50 p-4 rounded-lg shadow">
        <h3 class="font-bold">Conversões</h3>
        <p class="text-2xl">24%</p>
      </div>
    </div>
    
    <!-- Gráficos ocupando diferentes tamanhos -->
    <div class="grid grid-cols-12 gap-4">
      <div class="col-span-12 lg:col-span-8 bg-gray-50 p-4 rounded-lg">
        Gráfico Principal
      </div>
      <div class="col-span-12 lg:col-span-4 bg-gray-50 p-4 rounded-lg">
        Gráfico Secundário
      </div>
    </div>
  </main>
  
  <!-- Rodapé -->
  <footer class="col-span-12 bg-gray-200 p-4 mt-4 rounded-lg text-center">
    Dashboard © 2023
  </footer>
</div>
```

### 3. Layout de Página Complexa

```html
<div class="grid grid-cols-6 grid-rows-[auto_1fr_auto] min-h-screen">
  <!-- Cabeçalho -->
  <header class="col-span-6 bg-blue-600 text-white p-4">
    Cabeçalho do Site
  </header>
  
  <!-- Barra lateral -->
  <aside class="col-span-6 md:col-span-1 bg-gray-100 p-4">
    Navegação Lateral
  </aside>
  
  <!-- Conteúdo principal -->
  <main class="col-span-6 md:col-span-4 p-6">
    <h1 class="text-2xl font-bold mb-4">Conteúdo Principal</h1>
    <p>Este é o conteúdo principal da página...</p>
    
    <!-- Grid aninhado -->
    <div class="grid grid-cols-2 gap-4 mt-6">
      <div class="bg-gray-50 p-4 rounded-lg">Seção 1</div>
      <div class="bg-gray-50 p-4 rounded-lg">Seção 2</div>
      <div class="col-span-2 bg-gray-50 p-4 rounded-lg">Seção que ocupa toda largura</div>
    </div>
  </main>
  
  <!-- Barra lateral direita -->
  <aside class="col-span-6 md:col-span-1 bg-gray-100 p-4">
    Conteúdo Relacionado
  </aside>
  
  <!-- Rodapé -->
  <footer class="col-span-6 bg-gray-800 text-white p-4 text-center">
    Rodapé do Site © 2023
  </footer>
</div>
```

### 4. Cartões com Grid Areas

Usando CSS personalizado para nomear áreas em layouts complexos:

```html
<style>
  .dashboard {
    grid-template-areas:
      "header header header"
      "sidebar main main"
      "sidebar footer footer";
  }
  
  @media (max-width: 768px) {
    .dashboard {
      grid-template-areas:
        "header"
        "sidebar"
        "main"
        "footer";
    }
  }
</style>

<div class="grid dashboard grid-cols-3 gap-4">
  <header class="col-[header] bg-blue-500 p-4">Cabeçalho</header>
  <aside class="col-[sidebar] bg-blue-200 p-4">Barra Lateral</aside>
  <main class="col-[main] bg-white p-4">Conteúdo Principal</main>
  <footer class="col-[footer] bg-gray-200 p-4">Rodapé</footer>
</div>
```

## 🔄 Grid vs. Flexbox

### Quando usar Grid:
- Layouts bidimensionais (linhas E colunas)
- Posicionamento preciso dos elementos
- Layouts complexos que não se adaptam bem ao fluxo unidirecional
- Designs baseados em grades, como dashboards ou galerias

### Quando usar Flexbox:
- Layouts unidimensionais (linhas OU colunas)
- Distribuição de espaço entre itens em um eixo
- Alinhamento de itens em um container
- Componentes de navegação, barras de ferramentas

## 🎨 Personalização 

Para personalizar os utilitários de grid no `tailwind.config.js`:

```javascript
module.exports = {
  theme: {
    extend: {
      gridTemplateColumns: {
        // Colunas personalizadas
        'sidebar': '200px 1fr',
        'footer': '1fr auto',
      },
      gridTemplateRows: {
        // Linhas personalizadas
        'layout': 'auto 1fr auto',
      },
      gridColumn: {
        // Expansões de coluna personalizadas
        'span-16': 'span 16 / span 16',
      },
      gridRow: {
        // Expansões de linha personalizadas
        'span-8': 'span 8 / span 8',
      },
    }
  }
}
```

## 🔗 Links Úteis

- [Documentação de Grid no Tailwind](https://tailwindcss.com/docs/grid-template-columns)
- [Guia de CSS Grid da CSS-Tricks](https://css-tricks.com/snippets/css/complete-guide-grid/)
- [Grid Garden](https://cssgridgarden.com/) - Um jogo para aprender Grid
- [Can I Use - CSS Grid](https://caniuse.com/css-grid) - Compatibilidade com navegadores

---

[⬅️ Voltar para o início](../README.md)

<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=06B6D4&height=120&section=footer"/> 