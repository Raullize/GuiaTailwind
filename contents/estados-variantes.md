# Estados e Variantes no Tailwind CSS

![Estados e Variantes no Tailwind CSS](/images/estados-variantes.jpg)

## O que são Estados e Variantes?

No desenvolvimento web, os elementos da interface frequentemente mudam de aparência com base em diferentes estados - quando o cursor passa sobre eles, quando são clicados, ou quando estão desabilitados. O Tailwind CSS oferece um sistema poderoso de modificadores para estilizar esses diferentes estados sem precisar escrever CSS personalizado.

## Modificadores de Estado Comuns

### Hover

O modificador `hover:` permite aplicar estilos quando o cursor está sobre um elemento:

```html
<button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">
  Passe o mouse sobre mim
</button>
```

### Focus

O modificador `focus:` aplica estilos quando um elemento recebe foco:

```html
<input class="border border-gray-300 focus:border-blue-500 focus:ring focus:ring-blue-200 focus:ring-opacity-50 rounded-md" type="text">
```

### Active

O modificador `active:` estiliza elementos durante o clique:

```html
<button class="bg-green-500 hover:bg-green-600 active:bg-green-700 text-white py-2 px-4 rounded">
  Clique e segure
</button>
```

### Disabled

Combinado com classes de opacidade ou cores, você pode estilizar elementos desabilitados:

```html
<button class="bg-blue-500 text-white py-2 px-4 rounded disabled:opacity-50 disabled:cursor-not-allowed">
  Botão Desabilitado
</button>
```

## Variantes de Grupo

O Tailwind permite estilizar elementos filhos com base no estado do elemento pai usando variantes de grupo:

```html
<div class="group border p-4 hover:bg-gray-100 rounded">
  <h3 class="text-gray-700 group-hover:text-black">Título do cartão</h3>
  <p class="text-gray-500 group-hover:text-gray-700">Este conteúdo muda quando você passa o mouse sobre o cartão inteiro.</p>
</div>
```

## Combinando Modificadores

Você pode combinar diferentes modificadores para criar estilos mais específicos:

```html
<button class="bg-purple-500 hover:bg-purple-600 dark:bg-purple-700 dark:hover:bg-purple-800 text-white py-2 px-4 rounded">
  Combinando hover e dark mode
</button>
```

## Modificadores Responsivos com Estados

Você também pode combinar modificadores de responsividade com estados:

```html
<button class="bg-blue-500 md:hover:bg-red-500 lg:hover:bg-green-500 text-white py-2 px-4 rounded">
  Diferentes cores de hover em diferentes tamanhos de tela
</button>
```

## Estados para Formulários

### Placeholder

```html
<input 
  class="border rounded px-4 py-2 placeholder-gray-400 placeholder-opacity-75 focus:placeholder-transparent" 
  placeholder="Digite seu email"
>
```

### Checked

```html
<div class="flex items-center">
  <input type="checkbox" class="form-checkbox h-5 w-5 text-blue-600 checked:bg-blue-600 focus:ring-blue-500">
  <span class="ml-2">Opção selecionável</span>
</div>
```

### Invalid e Valid

```html
<input 
  class="border rounded px-4 py-2 invalid:border-red-500 valid:border-green-500" 
  type="email" 
  required
>
```

## Customizando Variantes

Você pode customizar ou adicionar variantes no arquivo `tailwind.config.js`:

```javascript
// tailwind.config.js
module.exports = {
  // ...
  variants: {
    extend: {
      backgroundColor: ['active', 'disabled'],
      borderColor: ['focus-visible'],
      opacity: ['disabled'],
    }
  },
}
```

## Variantes Avançadas

### Dark Mode

Tailwind suporta dark mode através do modificador `dark:`:

```html
<div class="bg-white dark:bg-gray-800 text-black dark:text-white p-4">
  Este conteúdo se adapta automaticamente ao modo escuro
</div>
```

Para habilitar o dark mode, configure no `tailwind.config.js`:

```javascript
// tailwind.config.js
module.exports = {
  darkMode: 'media', // ou 'class'
  // ...
}
```

### Variantes de Animação

Você pode aplicar animações em diferentes estados:

```html
<button class="transform transition duration-200 hover:scale-105 active:scale-95 bg-blue-500 text-white py-2 px-4 rounded">
  Botão Animado
</button>
```

## Exemplo Prático: Card Interativo

```html
<div class="group max-w-sm rounded overflow-hidden shadow-lg hover:shadow-xl transition-shadow duration-300">
  <img class="w-full" src="https://source.unsplash.com/random/300x200" alt="Card image">
  <div class="px-6 py-4">
    <div class="font-bold text-xl mb-2 group-hover:text-blue-600 transition-colors">Card Interativo</div>
    <p class="text-gray-700 text-base">
      Este card demonstra vários estados e interações usando Tailwind CSS.
    </p>
  </div>
  <div class="px-6 pt-4 pb-2">
    <button class="bg-blue-500 hover:bg-blue-700 focus:ring focus:ring-blue-300 active:bg-blue-800 text-white font-bold py-1 px-2 rounded">
      Clique aqui
    </button>
  </div>
</div>
```

## Exemplo Prático: Formulário com Estados

```html
<form class="max-w-md mx-auto p-6 bg-white rounded-lg shadow-md">
  <div class="mb-4">
    <label class="block text-gray-700 text-sm font-bold mb-2" for="username">
      Usuário
    </label>
    <input 
      class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:ring focus:border-blue-500 invalid:border-red-500"
      id="username" 
      type="text" 
      placeholder="Usuário" 
      required
    >
  </div>
  <div class="mb-6">
    <label class="block text-gray-700 text-sm font-bold mb-2" for="password">
      Senha
    </label>
    <input 
      class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 mb-3 leading-tight focus:outline-none focus:ring focus:border-blue-500"
      id="password" 
      type="password" 
      placeholder="******************"
    >
  </div>
  <div class="flex items-center justify-between">
    <button 
      class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded focus:outline-none focus:shadow-outline active:bg-blue-800 disabled:opacity-50 disabled:cursor-not-allowed"
      type="submit"
    >
      Entrar
    </button>
    <a class="inline-block align-baseline font-bold text-sm text-blue-500 hover:text-blue-800" href="#">
      Esqueceu a senha?
    </a>
  </div>
</form>
```

## Dicas e Melhores Práticas

1. **Priorize a ordem dos modificadores**: Coloque modificadores na ordem: responsivo → estado → variante. Exemplo: `md:hover:bg-blue-500`.

2. **Evite excessos**: Muitos modificadores podem tornar o HTML difícil de ler. Considere extrair classes complexas para componentes ou use `@apply` em um arquivo CSS.

3. **Selecione os modificadores apropriados**: Use apenas os modificadores necessários para evitar problemas de desempenho.

4. **Teste em diferentes dispositivos**: Verifique se os estados funcionam corretamente em dispositivos de toque e diferentes navegadores.

## Recursos Úteis

- [Documentação oficial sobre estados](https://tailwindcss.com/docs/hover-focus-and-other-states)
- [Lista completa de pseudo-classes suportadas](https://tailwindcss.com/docs/hover-focus-and-other-states#pseudo-class-reference)
- [Customizando variantes](https://tailwindcss.com/docs/configuring-variants)

## Conclusão

Os modificadores de estado do Tailwind CSS oferecem uma maneira eficiente de criar interfaces interativas e responsivas sem escrever CSS personalizado. Ao dominar essas variantes, você pode criar experiências de usuário ricas e profissionais mantendo seu código limpo e fácil de manter. 