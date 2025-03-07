# Aula 3 / Parte 2 - Instalação e Uso básico

## Instalação via Vite
Agora iremos conhecer um empacotador que tem se tornado a **escolha mais popular** já há alguns anos no mercado, o Vite. Atualmente, essa é a minha recomendação para se trabalhar na web, visto que ele é **extremamente simples**, **performático** e consegue ser melhor que seus concorrentes em **quase todos os sentidos**.

1. Vamos começar criando uma nova pasta separada para que você possa manter os 2 projetos para estudar futuramente. Crie a pasta 02-instalacao-e-uso-vite e inicialize o npm. Além disso, instale também o Vite:

Obs.: o Vite possui uma ferramente de linha de comando para ajudar na criação dos seus projetos, mas aqui, para fins de simplicidade, instalaremos manualmente.

```
npm init -y
npm i --save-dev vite
```

2. Crie o arquivo de configuração vite.config.js na raiz do projeto. O Vite foi desenvolvido para se beneficiar dos ESModules, portanto podemos usar essa sintaxe ao trabalhar com ele:

```js
import { resolve } from 'path'

export default {
  root: resolve(__dirname, 'src'),
  build: { outDir: '../dist' },
  server: { port: 8080 }
}
```

3. Copie o arquivo src/index.htmldo projeto Webpack para este. Aproveitaremos o seu conteúdo e usaremos a mesma estrutura de pastas.

4. Crie também alguns scripts para agilizar a execução e *build* do projeto:

```json
{
  "name": "02-instalacao-e-uso-vite",
  "version": "1.0.0",
  "main": "index.js",
  "scripts": {
    "start": "vite",
    "build": "vite build"
  },
  "keywords": [],
  "author": "",
  "license": "ISC",
  "description": "",
  "devDependencies": {
    "vite": "^6.0.11"
  }
}
```

5. Isso é tudo o que precisamos para o Vite. Execute o comando npm starte veja que nosso servidor já funciona perfeitamente, com muito menos etapas que o Webpack.

6. Agora, para incluir o Bootstrap, instalamos os pacotes necessários:

```
npm i bootstrap @popperjs/core
npm i --save-dev sass@1.77.6
```

7. E então faremos o mesmo que no projeto com Webpack:
    1. incluiremos os estilos em src/scss/styles.scss
    ```scss
    @use "bootstrap/scss/bootstrap";
    ```

    2. incluiremos tudo em src/js/main.js
    ```js
    // Estilos do Bootstrap
    import '../scss/styles.scss'

    // Scripts do Bootstrap (necessário apenas para alguns componentes)
    import * as bootstrap from 'bootstrap'
    ```

8. Você poderá ver que o Bootstrap ainda não está funcionando. Isso ocorre porque no Vite fazemos a importação do módulo principal diretamente no arquivo HTML. Portanto só precisamos de uma pequena correção no arquivo src/index.html:

```html
<!DOCTYPE html>
<html lang="pt-BR">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Instalação e Uso do Bootstrap</title>

  <script type="module" src="./js/main.js"></script>
</head>

<!-- 
	O resto do código é exatamente o mesmo,
	apenas incluimos a tag <script type="module"> no <head>
-->
```