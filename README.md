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
- Baseado em Components: A componentização permite gerar funcionalidades que independem umas das outras mas que mantêm constante comunicação.


<h2>Ambiente de Desenvolvimento</h2>


Como foi dito, há formas distintas de utilizar o React, podendo ser simplesmente aplicado a um tag script em uma file HTML ou ter uma aplicação completamente voltada para seu uso. Tendo isso em mente, a seguir veremos o que é necessário para criar um projeto React, além de nos aprofundarmos nas características da ferramenta:


<h2>Node</h2>


Aplicações Web demandam o uso de uma série de recursos para diferentes funcionalidades, como packages e libs específicas. O Javascript, e por consequência libs que fazem uso deste, como o React, contam com o Node e seu package manager(npm) para tal. Sendo ele um host de inúmeros packages e bibliotecas de terceiros que disponibilizam recursos a serem utilizados no desenvolvimento. 

Dada esta necessidade, a documentação a seguir mostra como instalar o Node, além de introduzir o básico sobre a ferramenta. E também conta, com mais riqueza de detalhes, como desenvolver utilizando o ambiente Node: 


[Node](https://github.com/VictorSantos12/Node.js)


Para verificar as versões do Node e do npm instaladas, use respectivamente:

    node -v

<br>

    npm -v


Certifique-se de ter instalado uma versão do Node acima da 14.0.0 e 6+ do npm, já que versões antigas podem não conter recursos que serão utilizados nos exemplos adiante.


<h1>Criando um React App</h1>


Com a instalação do Node, já é possível criar uma aplicação React totalmente do zero. Para isso, acesse o diretório onde o projeto será criado, através do terminal, e execute um dos comandos a seguir:


<h3>npx</h3>
    

    npx create-react-app my-app


O [npx](https://medium.com/@maybekatz/introducing-npx-an-npm-package-runner-55f7d4bd282b) é um package runner que faz parte da versão 5.2+ e maiores do npm.


<h3>npm</h3>


    npm init react-app my-app


<h3>Yarn</h3>

    
    yarn create react-app my-app


O yarn é uma package manager alternativo ao npm, sendo bastante utilizada por desenvolvedores React.


O comando irá criar um diretório chamado my-app dentro da pasta atual. No diretório, será gerada a estrutura inicial da aplicação e algumas dependências:


    my-app
    |
    ├── README.md
    ├── node_modules ----------------- Node package lib
    ├── package.json ----------------- Dependency record
    ├── .gitignore
    |
    ├── public ----------------------- Public resources
    │   ├── favicon.ico -------------- App icon 
    │   ├── index.html --------------- Main HTML file
    │   └── manifest.json ------------ Basic app info            
    |
    └── src -------------------------- Components directory
        ├── App.css ------------------ App component style sheet
        ├── App.js ------------------- App component javascript file
        ├── App.test.js -------------- App component test file
        ├── index.css ---------------- Main CSS file
        ├── index.js ----------------- Main JS file
        ├── logo.svg ----------------- App icon
        └── setupTests.js ------------ Unit testing file


Sem qualquer configuração ou estrutura de compilação, o diretório apenas conta com o necessário para inicializar um React app. Uma vez que a instalação foi concluída, é possível fazer o run do projeto com um dos comandos a seguir:


    npm start

<br>

    yarn start 


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


Para termos o popular Hello World em tela, faremos uma pequena modificação no projeto criado. No arquivo index.js, que nada mais é que o principal arquivo .js da aplicação, a partir do qual toda a aplicação é renderizada, faremos a seguinte mudança:


    ReactDOM.render(                         ReactDOM.render(
      <React.StrictMode>                       <h1>Hello, world!</h1>,
        <App />                                document.getElementById('root')
      </React.StrictMode>,                   );
      document.getElementById('root')       
    );                                       


Após salvarmos as modificações, teremos um header "Hello, world!" em tela. Com este exemplo tivemos contato com recursos bastante importantes e caracteristicos do React, como o JSX, o ReactDOM, e a componentização, sobre os quais falaremos a seguir.


<h1>O que é JSX ?</h1>


A maior parte das aplicações e modelos de desenvolvimento separa lógica e UI, o JSX, ou Javascript Xml, é uma subversão dessa prática, sendo uma extensão da sintaxa do Javascript que se assemelha a uma linguagem de marcação, mas que mantém todos o rescursos de uma linguagem de programação.

Considere a seguinte declaração:


    const element = <h1>Hello, world!</h1>;


É comum pensar que a tag h1 teria o mesmo valor semântico das aspas em uma String, porém, não é o caso. O JSX matem o valor semântico de qualquer tag HTML em sua sintaxe, logo, caso a const element sofra instância, o valor acessado através dela será um header e seu children(texto nele contido). O mesmo pode ser dito de praticamente qualquer tag HTML quando aplicada ao JSX.

Disso pode-se concluir que o React tranta lógica e UI como uma única coisa, definida como element ou component, onde apenas os conceitos são separados em uma estrutura pouco acoplada. Porém, apesar das fortes recomendações, o uso do JSX não é obrigatório dentro de um projeto React, o que pode ser visto no exemplo a seguir:


    JSX ON                                JSX OFF

    const element = (                     const element = React.createElement(
      <h1 className="greeting">             'h1',
        Hello, world!                       {className: 'greeting'},
      </h1>                                 'Hello, world!'
    );                                    );

  
Uma diferença clara entre os dois exemplos é a simplificação da sitaxe do element, que passa a ser uma tag HTML comum quando o JSX é utilizado, e sua declaração é o suficiente para criá-lo. O uso do JSX também proporciona um código muito mais legível quando compadaro ao resultado obtido quando não utilizado, já que pode ser facilmente interpretado por quem tiver o mínimo de conhecimento sobre Javascript e HTML.


<h2>Babel</h2>


Diferente do Javascript e do HTML, que são diretamente interpretados pelo navegador, o JSX necessita de um transpilador para gerar, a partir dos elementos que compõem o template, o código equivalente em Javascript, tornando o React interpretável até mesmo por versões mais antigas do Internet Explorer. 

O React conta com várias ferramentas para suprir esta nessecidade, porém, a mais utilizada é o Babel. O Babel é famoso por compilar, ou transpilar, código ECMAScript 6 e versões mais modernas, que contam com novas funcionalidades não interpretáveis por todos os navegadores, em um código Javascript que possa ser interpretado por versões mais antigas e menos utilizadas, o que abrange a sintaxe do JSX. Esse processo pode ser visto no exemplo a seguir:


    (x, y) => {return x + y}


O babel converteria a arrow function do exemplo acima para versões mais antigas do Javascript da seguinte forma:


     // es2016                // es2015

     "use strict";            "use strict";
      
     (x, y) => {              (function (x, y) => {
       return x + y;            return x + y;
     }                        });


O processo de transpilação do Babel é dividido em três principais passos:

- PARSER: Converte o código em AST(Abstract Syntax Tree), mapeando todos os elementos presentes.
- TRANSFORMER: Manipula o AST gerado com base em um registro de possíbilidades de conversão.
- GENERATOR: Transforma o AST resultante do TRANSFORMER em um código Javascript otimizado para uso.


<h2>Sintaxe</h2>


Apesar das semelhanças com o HTML, o JSX se comporta de forma diferente, permitindo com que basicamente qualquer expressão Javascript possa ser utilizada em conjunto com estruturas de marcação. Com isso é pissível utilizar:


<h2>Expressões Dinâmicas</h2>


    let name = "Victor";
    let welcoming = <h1>Welcome, {name}!</h1>;

    ReactDOM.render(
      welcoming,
      document.getElementById('root')
    );


O que normalmente seria atrelado a um template string, é utilizado como children da tag, permitindo acessar valores através da sua instanciação dentro de chaves.


<h2>Operações Aritméticas</h2>


    const a = 10;
    const b = 11;
    const element = <h1>resultado: {(a + b) / 2}</h1>;
    
    ReactDOM.render(
      element,
      document.getElementById('root')
    );


Senguindo a regra de uso das chaves, operações envolvendo expressões Javascript também podem ser utilizadas.


<h2>Funções</h2>


    const name = "Victor";
    
    function getUserName(name) {
      return name;
    }
    
    const userName = <h1>{getUserName(name)}</h1>
    
    ReactDOM.render(
      userName,
      document.getElementById('root')
    );


No JSX, instâncias de funções também podem ser definidas como children de elementos HTML, permitindo passar,  por parâmetro, valores que serão utilizados.


<h2>Expressões Condicionais</h2>


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


Elementos HTML também podem ser retornados como valores em expressões condicionais, o que torna possível manipular a UI com base em tais expressões.


<h1>React DOM e a Renderização de Elementos</h1>


Dentre os processos da compilação de uma aplicação Web, a renderização de elementos DOM é o mais custozo, tendo que lidar com frame updating, animations, style sheet e entre outros elementos de User Interface, todos ao mesmo tempo. Assim sendo, atualizar um elemento por exemplo, demanda muito mais tempo e consumo de memória quando comparado ao processo de interpretação em single thread de uma .js file.

Divergindo dos documentos HTML diretamente renderizados pelo navegador, os React Components e os elementos que os produzem são objetos mais simples, cujo processo de interpretação é intermediado pelo próprio React, ou melhor, pelo React DOM, que é um equivalente ao DOM, porém, otimizado para interpretar código JSX e gerar o que por fim será interpratado pelo DOM. Observe o exemplo a seguir:


    function MyComponent() {
      return(
        <main>
          <h1 id="title">Hello, world!</h1>
        </main>
      )
    }


Os React Components em si serão mais bem abordados posteriormente, no momento o importante é entender como estes são renderizados e interpretados pelo React DOM, que no caso do exemplo acima seria o seguinte objeto:

    
    {
      type: "main",
      key: null,
      ref: null,
      "$$typeof": Symbol(rect.element),
      props: {
        children: {
          type: "h1",
          key: null,
          ref: null,
          props: {
            id: "title",
            children: "Hello, world!"
          }
        }
      }
    }


<h2>Render Method</h2>
    

O React DOM conta com o render method, este que será visto em praticamente qualquer component que renderize JSX elements. Ele segue a estrutura a seguir:

    
    ReactDOM.render(element, container[, callback])


Sendo uma instância da const render, que é um dos atributos do ReactDOM, o render method recebe dois parâmetros: o elemento a ser renderizado, podendo ser apenas um ou vários agrupados em um único; e um container que define onde a renderização irá ocorrer. A estrutura do render method pode ser vista em detalhes a seguir:


    const render: ReactDOM.Renderer
    (
      element: React.FunctionComponentElement<any> | React.FunctionComponentElement<any>[], 
      container: ReactDOM.Container, 
      callback?: () => void
    ) => void (+6 overloads)


Uma característica importante sobre o atributo container é que em aplicações que utilizam apenas o React, sempre haverá apesas um dele, e é a partir deste que toda a aplicação será renderizada e gerenciada pelo React DOM. Sendo chamado de root DOM node, que basicamente é uma div com o id root declarada na index.html da aplicação. O exemplo a seguir pode ser observado no my-app criado anteriormente:

    ...

    import App from './App';

    ...
    
    ReactDOM.render(
      <App />,
      document.getElementById('root')
    );


<h2>Virtual DOM</h2>


O React DOM ainda conta com o Virtual DOM, que consiste em uma cópia virtual dos elementos que compõem a estrutura da aplicação. Quando uma mudança de estado ocorre, o Virtual DOM detecta, através da sua cópia virtual, qual elemento foi atualizado, renderizando apenas o elemento que sofreu alterações:


<div align="center">
  <img src="https://user-images.githubusercontent.com/61476935/145583677-409f5cad-7984-427a-bf92-116ba7817479.png">
</div>


Considere o exemplo a seguir:


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


Nele, a função tick, que contém a execução do método ReactDom.render(), é chamada a cada segundo, resultando em uma constante atualização da interface:

<div align="center">
  <img src="https://user-images.githubusercontent.com/61476935/145409269-952df923-f079-4f03-b2db-ebb0edc8b8b2.gif">
</div>

Observe que mesmo que a cada segundo todo o elemento que descreve a interface seja recriado, apenas o texto que contém modificações é atualizado pelo React Dom, resultando em um maior desenpenho e menos consumo de memória.


<h1>Components</h1>


Sendo um dos aspectos mais importantes da estrutura do React, a componentização permite dividir a interface em partes independentes e reutilizáveis, pondendo ser planejadas de forma individual e isolada das demais.

A forma mais simples de declarar um React Component é criando uma função Javascript:


    function WelcomeMessage(props) {
      return <h1>Welcome, {props.name}!</h1>;
    }


O React também permite declarar components seguindo o modelo de classes do [ES6](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes), que contam com algumas features adicionais, as quais serão abordadas posteriormente:


    class WelcomeMessage extends React.Component {
      render() {
        return <h1>Welcome!</h1>;
      }
    }


Para declarar uma classe como um React component, como no exemplo acima, basicamente declaramos uma class ES6, que consiste na palavra-chave <i>class</i> seguida de um <i>namespace</i>. Seguidamente, essa classe deve ser declarada como um extends(herdeira) da classe React.Component, que permite identificá-la como um component dentro do template. Nela faremos uso do método render, que irá retornar um JSX equivalente aos elementos do component, podendo ser single-line, como no exemplo acima, ou multi-line, como no exemplo a seguir:


    class MyComponent extends React.Component {
      render() {
        return (
          <React.Fragment>
            <h1>1st element</h1>
            <h1>2nd element</h1>
          </React.Fragment>
        );
      }
    }


Uma expressão Multi-line JSX é definida dentro de parenteses, que por sua vez carregam um único element HTML, normalmente sendo um React.Fragment, uma div, ou apenas uma tag vazia(<></>), que irá conter os demais elementos como children.


<h2>Renderizando um Component</h2>


Os declarados elements no React, além de tags DOM, podem ser os chamados user-defined components, que nada mais são que uma instância de uma function ou class, equivalente a um component, dentro do tamplate. Sendo representada por uma tag que carrega o <i>namespace</i> do component. Por exemplo:


    <WelcomeMessage />


O <i>namespace</i>, ou nome de um component, deve sempre ser atribuído com base em seu próprio ponto de vista, evitando levar em conta o contexto em que será utilizado, além de seguir o camelCase como modelo de nomenclatura, que o diferencia dos elementos HTML padrão.


<h2>Props</h2>


As Props são valores imutáveis atribuídos aos components, semelhantes a parâmetros passados em funções, sendo exatamente isso caso o component em questão seja uma function. Em class components, as props são um override da propriedade props da classe React.Component:

                                                V
    (property) React.Component<any, any, any>.props: Readonly<any> & Readonly<{
        children?: React.ReactNode;
    }>


Props são essencialmente declaradas como type any, sendo passadas quando um component sofre uma instância, como por exemplo:


    <WelcomeMessage name="Victor" />


Caso o component em questão seja uma class, as props são acessadas através do identificador <i>this.</i>, onde o nome definido na instanciação do component será acessado por dot notation:

    ...

    <h1>Welcome, {this.props.name}!</h1>;

    ...


<h1>State</h1>


Um dos conceitos mais importantes do React é o State, já que o controle do processo de mudança é essencial no desenvolvimento de aplicações, e para ter tal controle, é importante entender como aplicar e utilizar o State em um component e como o seu ciclo de vida afeta essa funcionalidade. 

Em um exemplo anterior, foi visto como o React renderiza, através do Virtual DOM, especificamente os elementos que sofreram alterações. Também foi mostrado uma única forma de atualizar a interface, que é utilizando o ReactDOM.render() method. A seguir iremos entender como aplicar o State ao mesmo exemplo para que ele se autogerencie e atualize a UI quando a mudança ocorrer.

Considere a função, ou Component, tick anteriormente vista:


    function tick() {
      const element = (
        <div>
          <h1>Hello, world!</h1>
          <h2>It is {new Date().toLocaleTimeString()}.</h2>
        </div>
      );
      ReactDOM.render(
        element,
        document.getElementById('root')
      );
    }
    
    setInterval(tick, 1000);


Como já foi definido, a atualização neste exemplo só ocorre porque todo o component sofre um re-render a cada segundo, tempo definido no método setInterval(). Para iniciar, faremos o processo de encapsulamento de como o component é estruturado:


    function Clock(props) {
      return (
        <div>
          <h1>Hello, world!</h1>
          <h2>It is {props.date.toLocaleTimeString()}.</h2>
        </div>
      );
    }
    
    function tick() {
      ReactDOM.render(
        <Clock date={new Date()} />,
        document.getElementById('root')
      );
    }
    
    setInterval(tick, 1000);


Essa atualização ainda conta com um problema, já que atualizar a UI a partir de um component específico é de responsabilidade do próprio, neste caso a função Clock. Ao aplicar o state, o component será chamado apenas uma vez, se atualizando por conta própria. Para utilizarmos o state, iremos converter a função Clock em uma classe ES6, assim sendo possível entender na prática como utilizar o state atrelado ao lifecycle de um React Component:


    class Clock extends React.Component {
      render() {
        return (
          <div>
            <h1>Hello, world!</h1>
            <h2>It is {this.props.date.toLocaleTimeString()}.</h2>
          </div>
        );
      }
    }


<h1>LifeCycle</h1>


Como mencionado anteriormente, o uso de classes, e por conseguinte da orientação a objetos no processo de criação dos React Components, dá a esses components recursos que funções não possuem: os chamados lifecycle methods. Os lifecycle methods são utilizados no processo controle de fluxo de dados atrelados ao component em questão, permitido criar um ciclo de vida para o mesmo. Os lifecycle methods podem ser divididos nos seguintes grupos:


<h2>Mounting</h2>


O Mounting agrupa os métodos utilizados quando a instância de um component é criada, basicamente sendo os responsáveis por inicializar as estrutura do component. Eles são chamados na seguinte ordem:


- [constructor](https://pt-br.reactjs.org/docs/react-component.html#constructor)

- [static getDerivedStateFromProps()]()

- [render()]()

- [componentDidMount()]()


<h2>Updating</h2>


- []()
- []()
- []()

<h2>Unmounting</h2>


- []()


<h2>Error Handling</h2>


- []()


<h1>State & LifeCycle</h1>


- []()



