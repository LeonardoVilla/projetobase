# Guia de Criação de Projeto Laravel com Vite, TailwindCSS e Bootstrap

<p align="center"><a href="https://laravel.com" target="_blank"><img src="https://raw.githubusercontent.com/laravel/art/master/logo-lockup/5%20SVG/2%20CMYK/1%20Full%20Color/laravel-logolockup-cmyk-red.svg" width="400" alt="Laravel Logo"></a></p>

---

## 🚀 Sobre o Projeto

Este guia tem como objetivo auxiliar na criação de um projeto **Laravel** integrado com **Vite**, **TailwindCSS** e **Bootstrap**, utilizando o seguinte arquivo `package.json` como referência:

```json
{
    "$schema": "https://json.schemastore.org/package.json",
    "private": true,
    "type": "module",
    "scripts": {
        "build": "vite build",
        "dev": "vite"
    },
    "devDependencies": {
        "@tailwindcss/vite": "^4.0.0",
        "axios": "^1.11.0",
        "concurrently": "^9.0.1",
        "laravel-vite-plugin": "^2.0.0",
        "tailwindcss": "^4.0.0",
        "vite": "^7.0.7"
    },
    "dependencies": {
        "@popperjs/core": "^2.11.8",
        "bootstrap": "^5.3.8"
    }
}
```

---

## ⚙️ Passo a Passo para Criar o Projeto

### 1️⃣ Criar um novo projeto Laravel

```bash
composer create-project laravel/laravel nome-do-projeto
cd nome-do-projeto
```

### 2️⃣ Instalar dependências do Node.js

Certifique-se de ter o **Node.js** e **npm** instalados. Em seguida, rode:

```bash
npm init -y
```

### 3️⃣ Instalar as bibliotecas necessárias

Execute o seguinte comando para instalar todas as dependências listadas no `package.json`:

```bash
npm install @tailwindcss/vite@^4.0.0 axios@^1.11.0 concurrently@^9.0.1 laravel-vite-plugin@^2.0.0 tailwindcss@^4.0.0 vite@^7.0.7 @popperjs/core@^2.11.8 bootstrap@^5.3.8
```

### 4️⃣ Configurar o Vite no Laravel

No arquivo `vite.config.js`, adicione o seguinte conteúdo:

```js
import { defineConfig } from 'vite';
import laravel from 'laravel-vite-plugin';

export default defineConfig({
    plugins: [
        laravel({
            input: ['resources/css/app.css', 'resources/js/app.js'],
            refresh: true,
        }),
    ],
});
```

### 5️⃣ Configurar o TailwindCSS

Inicialize o TailwindCSS com:

```bash
npx tailwindcss init -p
```

Edite o arquivo `tailwind.config.js` e adicione:

```js
export default {
  content: [
    './resources/**/*.blade.php',
    './resources/**/*.js',
    './resources/**/*.vue',
  ],
  theme: {
    extend: {},
  },
  plugins: [],
}
```

No arquivo `resources/css/app.css`, inclua:

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

### 6️⃣ Configurar o Bootstrap

Adicione o import do Bootstrap no arquivo `resources/js/app.js`:

```js
import 'bootstrap/dist/css/bootstrap.min.css';
import 'bootstrap';
```

### 7️⃣ Executar o servidor de desenvolvimento

Em dois terminais diferentes, execute:

**Terminal 1 (Laravel):**
```bash
php artisan serve
```

**Terminal 2 (Vite):**
```bash
npm run dev
```

Para rodar ambos simultaneamente, você pode usar o `concurrently`:

```bash
npx concurrently "php artisan serve" "npm run dev"
```

---

## 📦 Build de Produção

Para gerar a versão otimizada do front-end:

```bash
npm run build
```

---

## 📚 Documentação Oficial

- [Laravel](https://laravel.com/docs)
- [Vite](https://vitejs.dev/)
- [TailwindCSS](https://tailwindcss.com/docs)
- [Bootstrap](https://getbootstrap.com/)

---

## 🧾 Licença

Este projeto segue a licença [MIT](https://opensource.org/licenses/MIT).

---

💡 **Dica:** Este setup é ideal para aplicações Laravel modernas com front-end reativo e performance otimizada.


**Biblioteca de Autenticação**
composer require laravel/breeze --dev
php artisan breeze:install livewire
npm install && npm run dev
php artisan migrate

**Tradução para pt-br**
https://github.com/lucascudo/laravel-pt-BR-localization.git