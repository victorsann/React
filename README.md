<div align="center">
 <img src="https://user-images.githubusercontent.com/61476935/145215309-c29e1f65-94c4-4a72-b41b-c90666210213.png">
</div>

<br>

<img src="https://img.shields.io/static/v1?label=React&message=Library&color=blue&style=for-the-badge&logo=React"/>


O React é uma biblioteca Javascript de funcionalidades para desenvolver web interfaces. Criado e mantido pelo Facebook, o React tem permanecido no topo da lista de ferramentas mais utilizadas pelos desenvolvedores, estando presente em grandes projetos como o Facebook, Whatsapp, Twetter, Yahoo Mail e até mesmo no Netflix.


<h2>Características Básicas</h2>


Com uma estrutura declarativa e reativa baseada em components, o React possui flexibilidade suficiente para ser utilizado em pequenos trechos de uma aplicação ou para criar SPA's robustas. O uso desse modelo é vantajoso pois:


- Declarativo: O React ópta por manter um processo de desenvolvimento declarativo, graças a facilidade de depuração e maior previsibilidade com relação ao código que o paradigma oferece.
- Reativo: Dando nome a biblioteca, a reatividade permite manter um fluxo de informações e de mudança de estados bastante fluido.
- Baseado em Componentes: A componentização permite gerar funcionalidades que independem umas das outras mas que mantêm constante comunicação.


<h2>Ambiente de Desenvolvimento</h2>


Como foi dito, há formas distintas de utilizar o React, podendo ser simplesmente aplicado a um tag script em uma file HTML ou ter uma aplicação completamente voltada para seu uso. Tendo isso em mente, a seguir veremos o que é necessário para criar uma single-page application em React do zero, e como ela irá se comportar:


<h2>Node</h2>


Aplicações Web demandam o uso de uma série de recursos para diferentes funcionalidades, como packages e libs específicas. O Javascript, e por consequência, aplicações que fazem uso deste contam com o Node e seu package manager(npm) para tal. Sendo este um host de inúmeros packages e bibliotecas de terceiros que proporcionam inúmeros recurso a serem utilizados no desenvolvimento. 

Dada esta necessidade, a documentação a seguir mostra como instalar o Node e define algumas características importantes da ferramenta: [Node](https://github.com/VictorSantos12/Node.js)

Para verificar as versões do Node e do npm isntaladas, use respectivamente:

    node -v

<br>

    npm -v


Certifique-se de ter instalado uma versão do Node acima da 14.0.0 e da 6+ do nmp, já que versões antigas podem não conter recursos que serão utilizados nos exemplos adiante.


<h1>Criando um React App</h1>


Após a instalação do Node, já é possível criar uma aplicação React totalmente do zero. Para isso, acesse o diretório onde o projeto será criado, através do terminal, e execute um dos comando a seguir:


<h3>npx</h3>
    

    npx create-react-app my-app


O [npx](https://medium.com/@maybekatz/introducing-npx-an-npm-package-runner-55f7d4bd282b) é um package runner que faz parte da versão 5.2+ e maiores do npm.


<h3>npm</h3>


    npm init react-app my-app


<h3>Yarn</h3>

    
    yarn create react-app my-app


O comando irá criar um diretório chamado my-app dentro da pasta atual. No diretório, será gerada a estrutura inicial da aplicação e algumas dependências, as quais serão mais bem abordadas adiante:


    my-app
    ├── README.md
    ├── node_modules
    ├── package.json
    ├── .gitignore
    ├── public
    │   ├── favicon.ico
    │   ├── index.html
    │   └── manifest.json
    └── src
        ├── App.css
        ├── App.js
        ├── App.test.js
        ├── index.css
        ├── index.js
        ├── logo.svg
        └── serviceWorker.js
        └── setupTests.js


Sem qualquer configuração ou estrutura de compilação, o diretório apenas conta com o necessário para inicializar um React app. Uma vez que a instalação foi concluída, é possível fazer o run do projeto com um dos comandos a seguir:


    yarn start

<br>

    npm start 


Como resultado, temos uma aplicação React rodando localmente em modo de desenvolvimento:


    Compiled successfully!
    
    You can now view my-app in the browser.
    
      Local:            http://localhost:3000
      On Your Network:  http://10.201.0.3:3000
    
    Note that the development build is not optimized.
    To create a production build, use yarn build.


<div align="center">
  <img src="https://user-images.githubusercontent.com/61476935/145259691-53cd2714-5c28-4c35-a913-9df01103c4b3.gif" style="border-radius: 100%;">
</div>

