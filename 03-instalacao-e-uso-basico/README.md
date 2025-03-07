# Aula 3 - Instalação e Uso Básico

## Instalação via CDN
Primeiro, vamos conhecer como instalar e usar o Bootstrap via CDN. Essa é a forma mais fácil, porém **mais limitada** para se trabalhar com o Bootstrap, pois apenas incluimos os arquivos completos de CSS e JS, **sem possibilidade de modularização** e qualquer customização deve ser feita **sobrescevendo os estilos padrão**, o que é **ineficiente**.

1. Usar o Bootstrap via CDN é simples. Primeiro, crie um arquivo HTML básico:
```html
<!DOCTYPE html>
<html lang="pt-BR">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Instalação e Uso do Bootstrap</title>
</head>

<body>
  <div>
    <h1>Título Principal (H1)</h1>
    <h2>Subtítulo (H2)</h2>
    <h3>Seção menor (H3)</h3>
    <h4>Subseção (H4)</h4>
    <h5>Detalhes (H5)</h5>
    <h6>Notas (H6)</h6>

    <p>Este é um parágrafo de exemplo. Você pode <strong>destacar texto</strong> em negrito ou <em>itálico</em>.</p>

    <p>Aqui está um <a href="#">link de exemplo</a> para testar os estilos de links.</p>

    <h2>Listas</h2>
    <ul>
      <li>Item da lista não ordenada 1</li>
      <li>Item da lista não ordenada 2</li>
      <li>Item da lista não ordenada 3</li>
    </ul>
    <ol>
      <li>Item da lista ordenada 1</li>
      <li>Item da lista ordenada 2</li>
      <li>Item da lista ordenada 3</li>
    </ol>

    <h2>Imagem</h2>
    <img src="<https://unsplash.it/1280/360>" alt="Imagem de Exemplo">

    <h2>Tabela</h2>
    <table>
      <tr>
        <th>Nome</th>
        <th>Idade</th>
        <th>Cidade</th>
      </tr>
      <tr>
        <td>Ana</td>
        <td>25</td>
        <td>São Paulo</td>
      </tr>
      <tr>
        <td>João</td>
        <td>30</td>
        <td>Rio de Janeiro</td>
      </tr>
    </table>

    <h2>Formulário</h2>
    <form>
      <label for="nome">Nome:</label>
      <input type="text" id="nome" name="nome">

      <label for="email">Email:</label>
      <input type="email" id="email" name="email">

      <label for="mensagem">Mensagem:</label>
      <textarea id="mensagem" name="mensagem"></textarea>

      <button type="submit">Enviar</button>
    </form>
  </div>
</body>

</html>
```

2. Agora, acesse o site do Bootstrap em https://getbootstrap.com/ e role para baixo até encontrar os links de CDN:

Obs.: No futuro é possível que o site do Bootstrap seja atualizado e fique um pouco diferente da imagem abaixo, mas é fundamental que você **obtenha os links de CDN no site oficial**, assim você garante que terá **links atualizados** e **funcionando corretamente**. Evite copiar o os links deste material.

3. Copie as tags de inclusão do CSS para o `head` e do JavaScript para o final do `body`:
```html
<!DOCTYPE html>
<html lang="pt-BR">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Instalação e Uso do Bootstrap</title>

  <link href="<https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css>" rel="stylesheet"
    integrity="sha384-QWTKZyjpPEjISv5WaRU9OFeRpok6YctnYmDr5pNlyT2bRjXh0JMhjY6hW+ALEwIH" crossorigin="anonymous">
</head>

<body>
  <div>
		<!-- ... -->
  </div>

  <script src="<https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js>"
    integrity="sha384-YvpcrYf0tY3lHB60NNkmXc5s9fDVZLESaAA55NDzOxhy9GkcIdslK1eN7N6jIeHz"
    crossorigin="anonymous"></script>
</body>

</html>
```

4. Agora basta ir até o navegador e verificar que o visual já está diferente. Além dos estilos base, podemos começar a usar qualquer classe disponível no Bootstrap, como no código abaixo:
```html
<!-- ... -->

<body class="bg-light">
  <div class="container py-5">
    <h1>Título Principal (H1)</h1>
    <h2>Subtítulo (H2)</h2>
    <h3>Seção menor (H3)</h3>
    <h4>Subseção (H4)</h4>
    <h5>Detalhes (H5)</h5>
    <h6>Notas (H6)</h6>

    <p>Este é um parágrafo de exemplo. Você pode <strong>destacar texto</strong> em negrito ou <em>itálico</em>.</p>

    <p>Aqui está um <a href="#">link de exemplo</a> para testar os estilos de links.</p>

    <h2>Listas</h2>
    <ul>
      <li>Item da lista não ordenada 1</li>
      <li class="text-success">Item da lista não ordenada 2</li>
      <li>Item da lista não ordenada 3</li>
    </ul>
    <ol>
      <li>Item da lista ordenada 1</li>
      <li>Item da lista ordenada 2</li>
      <li class="text-danger">Item da lista ordenada 3</li>
    </ol>

    <h2>Imagem</h2>
    <img src="<https://unsplash.it/1280/360>" alt="Imagem de Exemplo" class="img-fluid mb-5">

    <h2>Tabela</h2>
    <table class="table">
      <tr>
        <th>Nome</th>
        <th>Idade</th>
        <th>Cidade</th>
      </tr>
      <tr>
        <td>Ana</td>
        <td>25</td>
        <td>São Paulo</td>
      </tr>
      <tr>
        <td>João</td>
        <td>30</td>
        <td>Rio de Janeiro</td>
      </tr>
    </table>

    <h2>Formulário</h2>
    <form>
      <label for="nome">Nome:</label>
      <input type="text" id="nome" name="nome" class="form-control mb-3">

      <label for="email">Email:</label>
      <input type="email" id="email" name="email" class="form-control mb-3">

      <label for="mensagem">Mensagem:</label>
      <textarea id="mensagem" name="mensagem" class="form-control mb-3"></textarea>

      <button type="submit" class="btn btn-primary">Enviar</button>
    </form>
  </div>

  <script src="<https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js>"
    integrity="sha384-YvpcrYf0tY3lHB60NNkmXc5s9fDVZLESaAA55NDzOxhy9GkcIdslK1eN7N6jIeHz"
    crossorigin="anonymous"></script>
</body>

</html>
```

## Instalação via Webpack
A forma mais recomendada de se trabalhar com o Bootstrap é em conjunto com **algum empacotador**. Se você acompanhou nossos módulos de JavaScript deve se lembrar do **Webpack**. Agora veremos como instalar o Bootstrap em um projeto gerenciado com Webpack.

1. Comece removendo os links da CDN, inicializando o npm no diretório e instalando as dependências necessárias para o Webpack:
```
npm init -y
npm i --save-dev webpack webpack-cli webpack-dev-server html-webpack-plugin
```

2. E então crie o arquivo webpack.config.js no diretório raiz com a configuração básica do Webpack:

```js
'use strict'

const path = require('path')
const HtmlWebpackPlugin = require('html-webpack-plugin')

module.exports = {
  mode: 'development',
  entry: './src/js/main.js',
  output: {
    filename: 'main.js',
    path: path.resolve(__dirname, 'dist')
  },
  devServer: {
    static: path.resolve(__dirname, 'dist'),
    port: 8080,
    hot: true
  },
  plugins: [
    new HtmlWebpackPlugin({ template: './src/index.html' })
  ]
}
```

3. Além disso, para organizar o projeto de acordo com o que acabamos de colocar no arquivo de configuração, efetue os seguintes passos:
    1 - crie o diretório src

    2 - mova o arquivo index.html para src/index.html

    3 - crie o diretório src/js e, dentro dele, o arquivo src/js/main.jspara servir como arquivo de entrada

4. Você ainda pode criar scripts para agilizar a execução do projeto:
```json
{
  "name": "01-instalacao-e-uso",
  "version": "1.0.0",
  "main": "index.js",
  "scripts": {
    "start": "webpack serve",
    "build": "webpack build --mode=production"
  },
  "keywords": [],
  "author": "",
  "license": "ISC",
  "description": "",
  "devDependencies": {
    "html-webpack-plugin": "^5.6.3",
    "webpack": "^5.97.1",
    "webpack-cli": "^6.0.1",
    "webpack-dev-server": "^5.2.0"
  }
}
```

5. Agora, instale o pacote do Bootstrap e suas dependências de desenvolvimento:

Obs.: O @popperjs/core é **opcional**, sendo usado apenas para alguns componentes específicos do Bootstrap. Se você não necessita desses componentes, pode instalar **apenas o Bootstrap**. Aqui seguiremos a instalação completa para fins de demonstração.

Obs².: O **Sass** é um **requisito** do Bootstrap pois ele é todo desenvolvido nessa linguagem. Em aulas posteriores falaremos mais a fundo sobre ele. Por enquanto, apenas entenda que o loader é necessário para gerar o código final de produção, assim como as outras dependeências de desenvolvimento.

Obs³.: No momento da produção desse curso, o Bootstrap na **versão 5.3.3** possui uma leve incompatibiliade que resulta em **avisos não-críticos** com versões do Sass a **partir da 1.77.7**, portanto, se você estiver o usando o Bootstrap 5.3.3, **instale manualmente o Sass 1.77.6**.

```
npm i bootstrap @popperjs/core
npm i --save-dev autoprefixer css-loader postcss-loader sass@1.77.6 sass-loader style-loader
```

6. Para finalizar, crie o diretório src/scss para guardar os estilos. Nessa pasta aprenderemos futuramente a modificar os estilos do Bootstrap, mas por enquanto iremos usar os estilos padrão. Crie o arquivo src/scss/styles.scss e importe os estilos do Bootstrap:

Obs.: este caminho referencia os arquivos do Bootstrap na pasta node_modules.

```scss
@use 'bootstrap/scss/bootstrap';
```

7. Por fim, como já conhecemos do Webpack, é necessário importar os estilos no arquivo JavaScript de entrada src/js/main.js:

```js
// Estilos do Bootstrap
import '../scss/styles.scss'

// Scripts do Bootstrap (necessário apenas para alguns componentes)
import * as bootstrap from 'bootstrap'
```

8. Acesse https://localhost:8080/ e veja que o Bootstrap voltou a funcionar normalmente no site.