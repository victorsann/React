<div align="center">
 <img src="https://user-images.githubusercontent.com/61476935/145215309-c29e1f65-94c4-4a72-b41b-c90666210213.png">
</div>

<br>

<img src="https://img.shields.io/static/v1?label=React&message=Library&color=blue&style=for-the-badge&logo=React"/>


O React é uma biblioteca de funcionalidades para desenvolver web interfaces. Criado e mantido pelo Facebook, o React tem permanecido no topo da lista de ferramentas mais utilizadas pelos desenvolvedores, estando presente em grandes projetos como o Facebook, Whatsapp, Twetter, Yahoo Mail e até mesmo no Netflix.


<h2>Características Básicas</h2>


Com uma estrutura declarativa e reativa baseada em components, o React possui flexibilidade suficiente para ser utilizado em pequenos trechos de uma aplicação ou para criar SPA's robustas. O uso desse modelo é vantajoso pois:


- Declarativo: O React ópta por manter um processo de desenvolvimento declarativo graças a facilidade de depuração e maior previsibilidade com relação ao código que o paradigma oferece.
- Reativo: Dando nome a biblioteca, a reatividade permite manter um fluxo de informações e de mudança de estado bastante fluido.
- Baseado em Componentes: A componentização permite gerar funcionalidades que independem umas das outras mas que mantêm constante comunicação.


<h2>Ambiente de Desenvolvimento</h2>


Como foi dito, há formas distintas de utilizar o React, podendo ser simplesmente aplicado a um tag script em uma file HTML ou ter uma aplicação completamente voltada para seu uso. Tendo isso em mente, a seguir veremos o que é necessário para criar uma single-page application em React do zero, e como ela irá se comportar:


<h2>Node</h2>


Aplicações Web demandam o uso de uma série de recursos para diferentes funcionalidades, como packages e libs específicas. O Javascript, e por consequência, aplicações que fazem uso deste contam com o Node e seu package manager(npm) para tal. Sendo este um host de inúmeros packages e bibliotecas de terceiros que proporcionam inúmeros recursos a serem utilizados no desenvolvimento. 

Dada esta necessidade, a documentação a seguir mostra como instalar o Node e define algumas características importantes da ferramenta: [Node](https://github.com/VictorSantos12/Node.js)

Para verificar as versões do Node e do npm instaladas, use respectivamente:

    node -v

<br>

    npm -v


Certifique-se de ter instalado uma versão do Node acima da 14.0.0 e 6+ do npm, já que versões antigas podem não conter recursos que serão utilizados nos exemplos adiante.


<h1>Criando um React App</h1>


Após a instalação do Node, já é possível criar uma aplicação React totalmente do zero. Para isso, acesse o diretório onde o projeto será criado, através do terminal, e execute um dos comandos a seguir:


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


<h1>Hello World</h1>


Para termos o popular Hello World em tela, faremos uma pequena modificação no projeto criado. No arquivo index.js, que nada mais é que o principal aquivo .js da aplicação, faremos a seguinda mudança:


    ReactDOM.render(                         ReactDOM.render(
      <React.StrictMode>                       <h1>Hello, world!</h1>,
        <App />                                document.getElementById('root')
      </React.StrictMode>,                   );
      document.getElementById('root')       
    );                                       


Após salvarmos as modificações, teremos um header "Hello, world!" em tela. Com este exemplo tivemos contato com recursos bastante importantes e caracteristicos do React, como o JSX, o ReactDOM, e a componentização, sobre os quais falaremos a seguir.


<h1>O que é JSX ?</h1>


É comum definirmos o HTML e o CSS como um padrão do desenvolvimento Web, o que não está incorreto, já que ambos possuem uma associação direta, onde é possível escrever código Javascript em uma file HTML utilizando a já citada tag script. Porém, é bastante comum separá-los como recursos totalmente distintos. O JSX, ou Javascript Xml, é uma subversão dessa prática, sendo uma extensão da sintaxa do Javascript, que se assemelha a uma linguagem de marcação, mas que mantém todos o rescursos.

Considere a seguinte declaração:


    const element = <h1>Hello, world!</h1>;


Ela não se define por uma atribuíção de string à uma constante, e tão pouco como uma constante que recebe um tag HTML, é a sintaxe básica do JSX, que não desassocia ambas as definições.

Em ferramentas como o Angular, o desacoplamento de lógica e UI é simplesmente o padrão. O React tranta ambos como uma única coisa, definida como componente, onde apenas os conceitos são separados em uma estrutura pouco acoplada. Porém, apesar das fortes recomendações, o JSX não é obrigatório dentro de um projeto React, o que podemos ver no exemplo a seguir:


    JSX ON                                                   JSX OFF

    class HelloMessage extends React.Component {             class HelloMessage extends React.Component {
      render() {                                               render() {
        return (                                                 return React.createElement(
          <div>                                                    "div",
            Olá, {this.props.name}!                                null,
          </div>                                                   "Ol\xE1, ",
        );                                                         this.props.name,
      }                                                            "!"
     }                                                           );
                                                               }
    ReactDOM.render(                                         }
      <HelloMessage name="Taylor" />,                       ReactDOM.render(React.createElement(HelloMessage, 
      document.getElementById('hello-example')              { name: "Victor" }), document.getElementById('hello-example'));
    );


Ambos possuem a mesma funcionalidade e printam o mesmo resultado, mas usam os recursos do React de forma distinta, como a simples declaração de um elemento(JSX ON) e a necessidade de definir sua criação antes de declará-lo(JSX OFF). Mas, apesar de não ser uma obrigatoriedade, faremos uso constante do JSX nos próximos passos, já que é uma recomendação bastante válida e característica da lib.


<h2>Babel</h2>


Diferente do Javascript e do HTML, que são diretamente interpretados pelo navegador, o JSX necessita de um transpilador para gerar, a partir dos elementos que compõem o template, o código equivalente em Javascript e HTML comuns, tornando o React interpretável até mesmo por versões mais antigas do Internet Explorer. 

O React conta com várias ferramentas para suprir esta nessecidade, porém, a mais utilizada é o Babel. O Babel é famoso por compilar, ou transpilar, código ECMAScript 6 e versões mais modernas, que contam com novas funcionalidades não interpretáveis por todos os navegadores, em um código Javascript que possa ser interpretado por versões mais antigas e menos utilizadas, o que abrange a sintaxe do JSX. Esse processo pode ser visto no exemplo a seguir:


    (x, y) => {return x + y}


O babel converteria a arrow function do exemplo acima para versões mais antiga do Javascript da seguinte forma:


     // es2016                // es2015

     "use strict";            "use strict";
      
     (x, y) => {              (function (x, y) => {
       return x + y;            return x + y;
     }                        });


O processo de transpilação do Babel é dividido em três principais passos:

- PARSER: Converte o código em AST(Abstract Syntax Tree), mapeando todos os elementos presentes.
- TRANSFORMER: Manipula o AST gerado com base em um registro de possíbilidades de conversão.
- Generator: Tranforma AST resultante do TRANSFORMER em um código Javascript otimizado para uso.ss


<h2>Sintaxe</h2>


Apesar das semelhanças com o HTML, o JSX se comporta de forma diferente. Uma dessas diferenças é a aceitação de expressões Javascript como parte do conteúdo da tag, podendo ser incorporada entre chaves({ }). Com isso é pissível:


<h3>Expressões Dinâmicas</h3>


    const name = "Victor";
    const welcoming = <h1>Welcome, {name}!</h1>;

    ReactDOM.render(
      welcoming,
      document.getElementById('root')
    );


<h3>Executar Operações</h3>


    const a = 10;
    const b = 11;
    const element = <h1>resultado: {(a + b) / 2}</h1>;
    
    ReactDOM.render(
      element,
      document.getElementById('root')
    );


<h3>Executar Funções</h3>


    const name = "Victor";
    
    function getUserName(name) {
      return name;
    }
    
    const userName = <h1>{getUserName(name)}</h1>
    
    ReactDOM.render(
      userName,
      document.getElementById('root')
    );


<h3>Expressões Condicionais</h3>


    function getGreeting(user) {
      if (user) {
        return <h1>Hello, {user}!</h1>;
      }
      return <h1>Hello, Stranger.</h1>;
    }
    
    ReactDOM.render(
      getGreeting("Victor"),
      document.getElementById('root')
    );


<h1>Renderização de Elementos</h1>


Elemento é a designação dada as partes que compõem a user interface, sendo basicamente uma descrição do que é visto em tela:

    
    const element = <h1>Hello, world</h1>;


Diferente de elementos DOM do navegador, elementos React são objetos simples que utilizam menos recursos. O React DOM é o responsável por atualizar o Document Object Model para exibir os elementos React. Além disso, aplicações React, normalmente, contam com um elemento chamado de root node, permitindo que o React DOM gerencie toda a aplicação a partir de um único ponto. E para rederizar um elemento React, passamos ambos elemento e root como parâmetros da função ReactDOM.render():

    
    const element = <h1>Hello, world</h1>;

    ReactDOM.render(
      element, 
      document.getElementById('root')
    );


<h2>Atualizando Elementos Renderizados</h2>


Elementos React são imutáveis. Uma vez que um elemento foi criado, não é possível mudar seu elementos children ou atributos. Podendo ser compadaro com um frame, quando um elemento é rederizado, ele representa a user interface em determinado ponto no tempo de execução. Até onde é possível imagianr, o único geito de atualizar a user interface é através da criação de um novo elemento. Considere o exemplo a seguir:


    function tick() {
      const element = (
        <div>
          <h1>Hello, world!</h1>
          <h2>It is {new Date().toLocaleTimeString()}.</h2>
        </div>
      );
      ReactDOM.render(element, document.getElementById('root'));
    }
    
    setInterval(tick, 1000);


Nele, a função tick, que contém a execução do método ReactDom.render(), é chamada a cada segundo, resultando em uma constante atualização da UI.


<h2>Só o Necessário é Atualizado</h2>


O React DOM compara cada elemento que compõe a interface com a versão anterior, atualizando apenas o necessário para gerar uma verão mais atual do DOM. É possível observar esta afirmação verificando a atualização contante do exemplo anterir no browser:

<div align="center">
  <img src="https://user-images.githubusercontent.com/61476935/145409269-952df923-f079-4f03-b2db-ebb0edc8b8b2.gif">
</div>

Mesmo que a cada segundo todo o elemento que descreve a interface seja recriado, apenas o texto que contém modificações é atualizado pelo React Dom.


<h1>Componentes</h1>


Sendo um dos aspectos mais importantes da composição do React, a componentização permite dividir a interface em partes independentes e reutilizáveis, pondendo ser planejadas de forma individual e isoladas das demais. Conceitualmente, components são semelhantes a funções, que aceitam inputs arbitrários(chamados de "props") e retornam elemento React cuja função é descrever como determinada tela ou parte desta deverá se comportar.

A forma mais simples de definir um component é declarando uma função Javascript:


    function Welcome(props) {
      return <h1>Hello, {props.name}</h1>;
    }


Porém, a forma mais comum de declarar um component é utilizando o modelo de classes do [ES6](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes), que contam com algumas features adicionais que veremos posteriormente:


    class Welcome extends React.Component {
      render() {
        return <h1>Hello, {this.props.name}</h1>;
      }
    }


Do ponto de vista do React, ambas classes e funções equivalem a um component. É possível observar esta ideia no App component gerado pelo projeto anterioemente criado:


    function App() {
      return (
        <div className="App">
          <header className="App-header">
            <img src={logo} className="App-logo" alt="logo" />
            <p>
              Edit <code>src/App.js</code> and save to reload.
            </p>
            <a
              className="App-link"
              href="https://reactjs.org"
              target="_blank"
              rel="noopener noreferrer"
            >
              Learn React
            </a>
          </header>
        </div>
      );
    }
    
    export default App;


Perceba que ele nada mais é que uma função retornando um JSX element, que é exportada e utilizada como base para a aplicação.


<h2>Renderizando Components</h2>


Ainda coms o App Component em mente, perceba que um elemento que o representa compõe os parâmetro declarados na render function do React Dom na index.js file:


    import App from './App';
    
    ...

    ReactDOM.render(
      <App />,
      document.getElementById('root')
    );


Esta representação demonstra uma das características do JSX, que é a criação de tags customizadas, cuja função é instanciar um component dentro da árvore de objetos DOM, fazendo com ele possa ser renderizado ou reaproveitado em diversos pontos da aplicação. Normalmente se associa ao HTML elementos DOM que representem tags HTML, como:

    
    const element = <div />


Contudo, elementos também podem representar os chamados user-defined components, como por exemplo:

    
    function Welcome(props) {
      return <h1>Hello, {props.name}</h1>;
    }
    
    const element = <Welcome name="Victor" />; // user-defined component
    
    ReactDOM.render(
      element,
      document.getElementById('root')
    );


<h2>Componentes de Composição</h2>


Os componentes podem se referir a outros componentes em sua saída. Isso nos permite usar a mesma abstração de componente para qualquer nível de detalhe. Um botão, um formulário, um diálogo, uma tela: nos React App's, todos são comumente expressos como componentes.

Por exemplo, podemos modificar o App component para que ele renderize o Welcome component multiplas vezes:


    function Welcome(props) {
      return <h1>Hello, {props.name}</h1>;
    }
    
    function App() {
      return (
        <div>
          <Welcome name="Sara" />
          <Welcome name="Cahal" />
          <Welcome name="Edite" />
        </div>
      );
    }
    
    ReactDOM.render(
      <App />,
      document.getElementById('root')
    );


<h2>Extraindo Components</h2>


É bastante comum que em uma coposição de tela vários components surjam. Caso uma tela demande uma grande quantidade de elementos, é recomendado que se extraia esses elementos e que se crie novos components a partir destes. Por exemplo, imagine o seguinte serário:

Em uma aplicação, considere o componente comentário, com determinadas informações sobre o usuário que o fez:

<div align="center">
 <img src ="https://user-images.githubusercontent.com/61476935/145455941-3e75eb02-0e37-46f2-943c-cb6ec5ec6d12.png">
</div>

Informações como o avatar, nome e o texto irão se repetir para cada comentário feito. Etão digamos que como ersultado do modelo, foi criado o seguinte component:


    function Comment(props) {
      return (
        <div className="Comment">
          <div className="UserInfo">
            <img className="Avatar"
              src={props.author.avatarUrl}
              alt={props.author.name}
            />
            <div className="UserInfo-name">
              {props.author.name}
            </div>
          </div>
          <div className="Comment-text">
            {props.text}
          </div>
          <div className="Comment-date">
            {formatDate(props.date)}
          </div>
        </div>
      );
    }


O exemplo não implica em mostrar problemas de má funcionalidade, mas sim de pouca eficiência em termos de reúso das pequenas partes que fazem parte do component. Portanto, criaremos novos components a partir do commet, facilitando o processo de reaproveitamento e de manutenção do código. Começando com o Avatar:


    function Avatar(props) {
      return (
        <img className="Avatar"
          src={props.user.avatarUrl}
          alt={props.user.name}
        />
      );
    }


Estando isolado dos demais, o Avatar não precisa saber que está sendo utilizado em um comentário, perfil e etc. O React recomenda nomear components com base em seu próprio ponto de vista, evitando levar em conta o contexto em que será utilizado. 

Agora, dentro da estrutura do Comment, temos uma quebra de informações. Já seria possíel utilizar o Avatar component, porém, o mesmo faz parte das informações do usuário, e por definição o UserInfo deve conter o Avatar:


    function UserInfo(props) {
      return (
        <div className="UserInfo">
          <Avatar user={props.user} />
          <div className="UserInfo-name">
            {props.user.name}
          </div>
        </div>
      );
    }


Essa quebrar permite simplificar ainda mais o Comment component, que passou a ser estruturado da seguinte forma:


    function Comment(props) {
      return (
        <div className="Comment">
          <UserInfo user={props.author} />
          <div className="Comment-text">
            {props.text}
          </div>
          <div className="Comment-date">
            {formatDate(props.date)}
          </div>
        </div>
      );
    }

