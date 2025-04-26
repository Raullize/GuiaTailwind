<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=06B6D4&height=120&section=header&fontSize=30&fontColor=fff&animation=twinkling&fontAlignY=35"/>

# 🔄 Tailwind CSS com React ⚛️

O Tailwind CSS funciona extremamente bem com React, proporcionando uma maneira eficiente de criar interfaces de usuário modernas e responsivas. Este guia mostrará como integrar e aproveitar ao máximo o Tailwind em seus projetos React.

## 🚀 Instalação e Configuração

### Create React App

Para projetos Create React App, você pode instalar o Tailwind CSS assim:

```bash
# Navegue para o seu projeto
cd meu-app-react

# Instale as dependências necessárias
npm install -D tailwindcss postcss autoprefixer

# Gere os arquivos de configuração
npx tailwindcss init -p
```

Configure o arquivo `tailwind.config.js`:

```javascript
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: [
    "./src/**/*.{js,jsx,ts,tsx}",
  ],
  theme: {
    extend: {},
  },
  plugins: [],
}
```

Adicione as diretivas Tailwind ao seu CSS principal (geralmente `src/index.css`):

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

### Next.js

Para projetos Next.js, a configuração é similar:

```bash
# Instale as dependências
npm install -D tailwindcss postcss autoprefixer

# Gere os arquivos de configuração
npx tailwindcss init -p
```

Configure o `tailwind.config.js`:

```javascript
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: [
    "./pages/**/*.{js,ts,jsx,tsx}",
    "./components/**/*.{js,ts,jsx,tsx}",
  ],
  theme: {
    extend: {},
  },
  plugins: [],
}
```

Adicione as diretivas Tailwind ao arquivo `styles/globals.css`:

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

## 🧩 Utilizando Tailwind em Componentes React

### Abordagem Básica

O uso mais simples do Tailwind com React é aplicar classes diretamente nos elementos JSX:

```jsx
function Button({ children }) {
  return (
    <button className="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">
      {children}
    </button>
  );
}
```

### Classes Condicionais

Você pode aplicar classes condicionalmente usando operadores ternários ou lógicos:

```jsx
function Button({ primary, disabled, children }) {
  return (
    <button 
      className={`
        font-bold py-2 px-4 rounded
        ${primary ? 'bg-blue-500 hover:bg-blue-700 text-white' : 'bg-gray-200 hover:bg-gray-300 text-gray-800'}
        ${disabled ? 'opacity-50 cursor-not-allowed' : ''}
      `}
      disabled={disabled}
    >
      {children}
    </button>
  );
}
```

### Usando o pacote classnames

O pacote `classnames` simplifica a manipulação de classes condicionais:

```bash
npm install classnames
```

```jsx
import classNames from 'classnames';

function Alert({ type, message }) {
  return (
    <div
      className={classNames(
        'border px-4 py-3 rounded relative',
        {
          'bg-red-100 border-red-400 text-red-700': type === 'error',
          'bg-green-100 border-green-400 text-green-700': type === 'success',
          'bg-blue-100 border-blue-400 text-blue-700': type === 'info',
        }
      )}
    >
      {message}
    </div>
  );
}
```

### Usando o pacote clsx (alternativa mais leve)

```bash
npm install clsx
```

```jsx
import clsx from 'clsx';

function Badge({ count, variant }) {
  return (
    <span className={clsx(
      'inline-flex items-center px-2.5 py-0.5 rounded-full text-xs font-medium',
      {
        'bg-red-100 text-red-800': variant === 'danger',
        'bg-green-100 text-green-800': variant === 'success',
        'bg-blue-100 text-blue-800': variant === 'info',
      }
    )}>
      {count}
    </span>
  );
}
```

## 🎨 Criando Componentes Reutilizáveis

### Componente de Botão

```jsx
import React from 'react';
import clsx from 'clsx';

function Button({ 
  children, 
  variant = 'primary', 
  size = 'md', 
  disabled = false, 
  className, 
  ...props 
}) {
  return (
    <button
      className={clsx(
        'font-medium rounded focus:outline-none focus:ring-2',
        {
          // Variantes
          'bg-blue-500 hover:bg-blue-600 focus:ring-blue-300 text-white': variant === 'primary',
          'bg-red-500 hover:bg-red-600 focus:ring-red-300 text-white': variant === 'danger',
          'bg-gray-200 hover:bg-gray-300 focus:ring-gray-300 text-gray-800': variant === 'secondary',
          
          // Tamanhos
          'text-xs py-1 px-2': size === 'sm',
          'text-sm py-2 px-4': size === 'md',
          'text-base py-2 px-6': size === 'lg',
          
          // Estado desativado
          'opacity-50 cursor-not-allowed': disabled,
        },
        className
      )}
      disabled={disabled}
      {...props}
    >
      {children}
    </button>
  );
}

export default Button;
```

Uso:

```jsx
import Button from './Button';

function App() {
  return (
    <div className="space-x-2">
      <Button>Padrão</Button>
      <Button variant="danger" size="sm">Pequeno</Button>
      <Button variant="secondary" size="lg" disabled>Desativado</Button>
    </div>
  );
}
```

### Componente de Card

```jsx
import React from 'react';
import clsx from 'clsx';

function Card({ title, children, className, ...props }) {
  return (
    <div 
      className={clsx(
        "bg-white rounded-lg shadow-md overflow-hidden",
        className
      )}
      {...props}
    >
      {title && (
        <div className="px-6 py-4 border-b border-gray-200">
          <h3 className="text-lg font-medium text-gray-900">{title}</h3>
        </div>
      )}
      <div className="p-6">
        {children}
      </div>
    </div>
  );
}

export default Card;
```

## 💅 Estilos Globais vs. Componentes

### Abordagem 1: @apply em arquivos CSS

Crie um arquivo `button.css`:

```css
.btn {
  @apply font-bold py-2 px-4 rounded;
}
.btn-blue {
  @apply bg-blue-500 text-white;
}
.btn-blue:hover {
  @apply bg-blue-700;
}
```

Importe e use em seu componente:

```jsx
import './button.css';

function LoginButton() {
  return (
    <button className="btn btn-blue">
      Entrar
    </button>
  );
}
```

### Abordagem 2: CSS-in-JS com styled-components e Twin.macro

Instale as dependências:

```bash
npm install styled-components twin.macro
```

Configure o babel:

```javascript
// babel-plugin-macros.config.js
module.exports = {
  twin: {
    preset: 'styled-components',
  },
}
```

Use em seus componentes:

```jsx
import tw, { styled } from 'twin.macro';

// Usando styled-components com Tailwind
const StyledButton = styled.button`
  ${tw`bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded`}
`;

// Ou usando o macro diretamente
const Button = tw.button`
  bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded
`;

function LoginForm() {
  return (
    <div>
      <Button>Entrar com Twin.macro</Button>
      <StyledButton>Entrar com Styled</StyledButton>
    </div>
  );
}
```

## 🧠 Organizando Estilos em Aplicações Maiores

### Componentes Compostos

```jsx
// Input.jsx
import React from 'react';

const Input = ({ className = '', ...props }) => (
  <input
    className={`border rounded px-3 py-2 focus:outline-none focus:ring-2 focus:ring-blue-500 ${className}`}
    {...props}
  />
);

const Label = ({ className = '', ...props }) => (
  <label
    className={`block text-sm font-medium text-gray-700 ${className}`}
    {...props}
  />
);

const ErrorMessage = ({ className = '', ...props }) => (
  <p
    className={`mt-1 text-sm text-red-600 ${className}`}
    {...props}
  />
);

// Atribuir subcomponentes
Input.Label = Label;
Input.Error = ErrorMessage;

export default Input;
```

Uso:

```jsx
import Input from './Input';

function SignupForm() {
  return (
    <div className="space-y-4">
      <div>
        <Input.Label htmlFor="name">Nome</Input.Label>
        <Input id="name" type="text" />
      </div>
      
      <div>
        <Input.Label htmlFor="email">Email</Input.Label>
        <Input 
          id="email" 
          type="email" 
          className="border-red-300" 
        />
        <Input.Error>Email inválido</Input.Error>
      </div>
    </div>
  );
}
```

### Context API para Temas

```jsx
// ThemeContext.jsx
import React, { createContext, useContext, useState } from 'react';

const ThemeContext = createContext();

export function ThemeProvider({ children }) {
  const [darkMode, setDarkMode] = useState(false);
  
  return (
    <ThemeContext.Provider value={{ darkMode, setDarkMode }}>
      <div className={darkMode ? 'dark' : ''}>
        <div className="bg-white dark:bg-gray-900 text-gray-900 dark:text-white min-h-screen">
          {children}
        </div>
      </div>
    </ThemeContext.Provider>
  );
}

export function useTheme() {
  return useContext(ThemeContext);
}
```

Uso:

```jsx
// App.jsx
import { ThemeProvider } from './ThemeContext';
import ThemeToggle from './ThemeToggle';

function App() {
  return (
    <ThemeProvider>
      <div className="p-4">
        <ThemeToggle />
        <h1 className="text-2xl font-bold">Meu App com Tema</h1>
        {/* Resto do app */}
      </div>
    </ThemeProvider>
  );
}

// ThemeToggle.jsx
import { useTheme } from './ThemeContext';

function ThemeToggle() {
  const { darkMode, setDarkMode } = useTheme();
  
  return (
    <button
      className="p-2 rounded-md bg-gray-200 dark:bg-gray-700"
      onClick={() => setDarkMode(!darkMode)}
    >
      {darkMode ? '☀️ Modo Claro' : '🌙 Modo Escuro'}
    </button>
  );
}
```

## 🔧 Ferramentas e Plugins Úteis

### 1. Suporte para Editor

Para o VSCode, instale a extensão "Tailwind CSS IntelliSense" para autocompletar classes, linting e visualização de cores.

### 2. tailwindcss/forms

Para estilizar elementos de formulário nativos:

```bash
npm install @tailwindcss/forms
```

```javascript
// tailwind.config.js
module.exports = {
  // ...
  plugins: [
    require('@tailwindcss/forms'),
  ],
}
```

### 3. tailwindcss/typography

Para estilizar conteúdo de texto (Markdown, CMS, etc.):

```bash
npm install @tailwindcss/typography
```

```javascript
// tailwind.config.js
module.exports = {
  // ...
  plugins: [
    require('@tailwindcss/typography'),
  ],
}
```

Uso:

```jsx
function BlogPost({ content }) {
  return (
    <article className="prose lg:prose-xl">
      <div dangerouslySetInnerHTML={{ __html: content }} />
    </article>
  );
}
```

## 📱 Exemplo de Aplicação Completa

Aqui está um exemplo simplificado de uma barra de navegação responsiva em React com Tailwind:

```jsx
import React, { useState } from 'react';
import { Link } from 'react-router-dom';

function Navbar() {
  const [isOpen, setIsOpen] = useState(false);
  
  return (
    <nav className="bg-gray-800">
      <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div className="flex items-center justify-between h-16">
          <div className="flex items-center">
            <div className="flex-shrink-0">
              <img
                className="h-8 w-8"
                src="/logo.svg"
                alt="Logo"
              />
            </div>
            <div className="hidden md:block">
              <div className="ml-10 flex items-baseline space-x-4">
                <Link
                  to="/"
                  className="text-white px-3 py-2 rounded-md text-sm font-medium"
                >
                  Início
                </Link>
                <Link
                  to="/produtos"
                  className="text-gray-300 hover:text-white px-3 py-2 rounded-md text-sm font-medium"
                >
                  Produtos
                </Link>
                <Link
                  to="/contato"
                  className="text-gray-300 hover:text-white px-3 py-2 rounded-md text-sm font-medium"
                >
                  Contato
                </Link>
              </div>
            </div>
          </div>
          
          <div className="md:hidden">
            <button
              onClick={() => setIsOpen(!isOpen)}
              className="inline-flex items-center justify-center p-2 rounded-md text-gray-400 hover:text-white hover:bg-gray-700 focus:outline-none focus:ring-2 focus:ring-inset focus:ring-white"
              aria-expanded="false"
            >
              <span className="sr-only">Abrir menu</span>
              {!isOpen ? (
                <svg
                  className="block h-6 w-6"
                  xmlns="http://www.w3.org/2000/svg"
                  fill="none"
                  viewBox="0 0 24 24"
                  stroke="currentColor"
                  aria-hidden="true"
                >
                  <path
                    strokeLinecap="round"
                    strokeLinejoin="round"
                    strokeWidth="2"
                    d="M4 6h16M4 12h16M4 18h16"
                  />
                </svg>
              ) : (
                <svg
                  className="block h-6 w-6"
                  xmlns="http://www.w3.org/2000/svg"
                  fill="none"
                  viewBox="0 0 24 24"
                  stroke="currentColor"
                  aria-hidden="true"
                >
                  <path
                    strokeLinecap="round"
                    strokeLinejoin="round"
                    strokeWidth="2"
                    d="M6 18L18 6M6 6l12 12"
                  />
                </svg>
              )}
            </button>
          </div>
        </div>
      </div>

      {isOpen && (
        <div className="md:hidden">
          <div className="px-2 pt-2 pb-3 space-y-1 sm:px-3">
            <Link
              to="/"
              className="text-white block px-3 py-2 rounded-md text-base font-medium"
            >
              Início
            </Link>
            <Link
              to="/produtos"
              className="text-gray-300 hover:text-white block px-3 py-2 rounded-md text-base font-medium"
            >
              Produtos
            </Link>
            <Link
              to="/contato"
              className="text-gray-300 hover:text-white block px-3 py-2 rounded-md text-base font-medium"
            >
              Contato
            </Link>
          </div>
        </div>
      )}
    </nav>
  );
}

export default Navbar;
```

## ⚡ Dicas de Desempenho

### 1. Purgando Estilos Não Utilizados

O Tailwind CSS v3+ já faz isso automaticamente desde que você configure corretamente o arquivo `tailwind.config.js`.

### 2. Dividindo Código (Code Splitting)

Carregue apenas o CSS necessário para cada rota:

```jsx
import React, { lazy, Suspense } from 'react';
import { BrowserRouter, Routes, Route } from 'react-router-dom';

// Componentes com carregamento sob demanda
const Home = lazy(() => import('./pages/Home'));
const Products = lazy(() => import('./pages/Products'));
const Contact = lazy(() => import('./pages/Contact'));

function App() {
  return (
    <BrowserRouter>
      <Suspense fallback={<div className="p-4">Carregando...</div>}>
        <Routes>
          <Route path="/" element={<Home />} />
          <Route path="/produtos" element={<Products />} />
          <Route path="/contato" element={<Contact />} />
        </Routes>
      </Suspense>
    </BrowserRouter>
  );
}
```

### 3. Memoizando Componentes

```jsx
import React, { memo } from 'react';

const ComplexComponent = memo(function ComplexComponent({ data }) {
  return (
    <div className="p-4 bg-white shadow rounded-lg">
      {/* Muitas classes Tailwind e lógica complexa */}
      {data.map(item => (
        <div key={item.id} className="flex items-center p-2 hover:bg-gray-100">
          {/* Conteúdo */}
        </div>
      ))}
    </div>
  );
});
```

## 🔗 Links Úteis

- [Documentação oficial do Tailwind com React](https://tailwindcss.com/docs/guides/create-react-app)
- [Tailwind CSS + React no GitHub](https://github.com/tailwindlabs/tailwindcss-setup-examples/tree/master/examples)
- [Componentes Headless para React](https://headlessui.dev/)
- [Heroicons - Ícones otimizados para Tailwind](https://heroicons.com/)
- [Twin.macro - Tailwind + Styled-components/Emotion](https://github.com/ben-rogerson/twin.macro)

---

[⬅️ Voltar para o início](../README.md)

<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=06B6D4&height=120&section=footer"/> 