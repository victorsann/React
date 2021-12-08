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


Aplicações Web demandam o uso de uma série de recursos para diferentes funcionalidades, como packages e libs específicas. O Javascript, e por consequência aplicações que fazem uso deste, contam com o Node e seu package manager(npm) para tal. Sendo este um host de inúmeros packages e bibliotecas de terceiros que proporcionam inúmeros recurso a serem utilizados no desenvolvimento. 

Dada esta necessidade, a documentação a seguir mostra como instalar o Node e define algumas características importantes da ferramenta: [Node](https://github.com/VictorSantos12/Node.js)


<h2>React App</h2>


Após a instalação do Node, já é possível criar uma aplicação React totalmente do zero. Para isso, acesse o diretório onde o projeto será criado, através do terminal, e execute o comando a seguir:

    
    npx create-react-app my-app


Um detalhe importante sobre o comando acima, provavelmente notado por quem já teve contato com o node package manager, é uso do npx, o que não se trata de um erro de digitação, mas sim de um package runner do próprio npm. 

Com o início do run, o processo de instalação de alguns recursos básicos será iniciado, resultando nos arquivos que irão compor o porojeto e que, posteriormente, serão abordados de forma detalhada. Além disso, perceba que, com o fim da instalação, algumas informações foram retornadas no terminal:


    Inside that directory, you can run several commands:
    
      yarn start
        Starts the development server.
    
      yarn build
        Bundles the app into static files for production.
    
      yarn test
        Starts the test runner.
    
      yarn eject
        Removes this tool and copies build dependencies, configuration files
        and scripts into the app directory. If you do this, you can’t go back!
    
    We suggest that you begin by typing:
    
      cd my-app
      yarn start
    
    Happy hacking!


Estas nada mais são que alguns comandos básicos para iniciar o processo de configuração do app, sendo eles comandos yarn(package maneger recomendado que também será explicado adiante). Seguindo as recomendações, acesse a pasta my-app e inicialize o app usando um dos comando a seguir:


    yarn start

<br>

    npm start 


Como resultado, temos uma aplicação React rodando localmente:


    Compiled successfully!
    
    You can now view my-app in the browser.
    
      Local:            http://localhost:3000
      On Your Network:  http://10.201.0.3:3000
    
    Note that the development build is not optimized.
    To create a production build, use yarn build.


<div align="center">
  <img src="https://user-images.githubusercontent.com/61476935/145259691-53cd2714-5c28-4c35-a913-9df01103c4b3.gif">
</div>
