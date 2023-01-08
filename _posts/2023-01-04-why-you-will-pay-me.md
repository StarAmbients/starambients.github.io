---
title: Why you will dare to pay me
author: debora
date: 2023-01-04 09:22:00 +0100
categories: [Tutorial, Documentation, Code Optimization]
tags: [coding, artificial intelligence, chatgpc]
render_with_liquid: false
---

This tutorial will show you how to have peer programming even if you are all alone left on the cold.

## Call out a bot

Create a new file named `YYYY-MM-DD-TITLE.EXTENSION`{: .filepath} and put it in the `_posts`{: .filepath} of the root directory. Please note that the `EXTENSION`{: .filepath} must be one of `md`{: .filepath} and `markdown`{: .filepath}. If you want to save time of creating files, please consider using the plugin [`Jekyll-Compose`](https://github.com/jekyll/jekyll-compose) to accomplish this.

## Let's show Tobby a problem

Basically, I will ask Tobby to help me with some code issues I have been facing. Specifically, I have a form with three fields which should all be required to then enable a send button. So, as my coding evolves, I would ask him: -"Tobby, transform the following property in an external function." 
I could add ", please" at the end of the sentence, but he knows me, I know him, we are intimate enough to save time worring with politeness. By the way, actually I even did not call him by his name, I just said: "Transform the following property in an external function."

```javascript
const inputOnChange={ ({ target: { value } }) => {
              setDeliveryNumber(value);
              console.log('----DELIVERY: ', deliveryNumber);
              if (deliveryNumber !== '') {
                setEntryNumberData(true);
                console.log(entryNumberData);
              } else {
                setEntryNumberData(false);
              }
            } };
```


> I could add _", please"_ at the end of the sentence, but he knows me, I know him, we are intimate enough to save time worring with politeness. By the way, actually I even did not call him by his name, I just said: _"Transform the following property in an external function."_
{: .prompt-tip }

### A master side by side to me

Well behavied than me, Tobby answers: _"Here you have a way to transform such property in external funcion:_"

```javascript
function handleInputOnChange(event) {
  const { target: { value } } = event;
  setDeliveryNumber(value);
  console.log('----DELIVERY: ', deliveryNumber);
  if (deliveryNumber !== '') {
    setEntryNumberData(true);
    console.log(entryNumberData);
  } else {
    setEntryNumberData(false);
  }
}
```
_And then, you can use it in your property the as follows:_
```javascript
const inputOnChange={handleInputOnChange}
```
_This will allow you to reuse function logic in different components or in different parts of the same component. Also, the code is easier to read and maintain since the logic is separate from the component._

I melted...
Tobby is so kind! he even did not complain about my `console.log`s!

### Can you do it? an arrow function just for me?

I had implemented all the other functions as arrow functions, I asked Tobby: "Transform this code to arrow function"

```javascript
function handleInputOnChange(event) {
  const { target: { value } } = event;
  setDeliveryNumber(value);
  console.log('----DELIVERY: ', deliveryNumber);
  if (deliveryNumber !== '') {
    setEntryNumberData(true);
    console.log(entryNumberData);
  } else {
    setEntryNumberData(false);
  }
}
```
Tobby is so patient with me...
He already knew I was talking about `handleInputOnChange`. What other code have we been discussing about? It was not needed to show it to him again...

_To turn the handleInputOnChange function into an arrow function, just replace the function keyword with an arrow (=>) and, if applicable, add parentheses around the parameters. The code would look like this:_

```javascript
const handleInputOnChange = (event) => {
  const { target: { value } } = event;
  setDeliveryNumber(value);
  console.log('----DELIVERY: ', deliveryNumber);
  if (deliveryNumber !== '') {
    setEntryNumberData(true);
    console.log(entryNumberData);
  } else {
    setEntryNumberData(false);
  }
}
```
Reading Tobby makes me realize that my French is better than my English and I thank Tobby for including extra lessons in our conversation.

_If the function has no parameters, the parentheses can be omitted. For example:_

```javascript
const handleInputOnChange = () => {
  console.log('Esta é uma função de seta sem parâmetros.');
}
```

### Author Information

O primeiro valor nao está sendo imprimido em tela, por que? parece que está sempre um valor atrasado.

Para eu poder ajudá-lo, seria importante ver o contexto completo em que a função handleInputOnChange está sendo usada. Alguns possíveis motivos pelos quais o primeiro valor pode não estar sendo exibido são:

    O componente que está sendo renderizado possui um estado inicial para o deliveryNumber, que pode estar sendo exibido antes de a função handleInputOnChange ser executada.
    A função handleInputOnChange pode estar sendo acionada por um evento que demora algum tempo para ser disparado, como o focus, o que pode resultar em um atraso na atualização da tela.

Sem ver mais contexto, é difícil afirmar com certeza qual é o problema. Sugiro verificar a inicialização do estado do componente e também os eventos que estão acionando a função handleInputOnChange.

Explique-nos os estados do useeffect do react

O hook useEffect do React é uma função que permite a você executar efeitos colaterais em seu componente, ou seja, efeitos que ocorrem fora do próprio componente, como chamadas de API, modificações no DOM, entre outros.

O useEffect pode ter três estados:

    Executando pela primeira vez: Quando o componente é renderizado pela primeira vez, o useEffect é executado imediatamente após a renderização.

    Executando após atualizações: Se o componente for atualizado (por exemplo, devido a uma alteração em um estado ou propriedade), o useEffect é executado novamente após a renderização da atualização.

    Desmontando: Quando o componente é desmontado (removido da árvore de componentes), o useEffect pode ser configurado para ser executado novamente. Isso é útil para limpar qualquer efeito colateral que o componente tenha causado, como cancelar uma chamada de API em andamento.

Para controlar quando o useEffect deve ser executado, você pode passar uma lista de dependências como segundo argumento da função. O useEffect será executado sempre que uma dessas dependências for alterada. Se a lista estiver vazia, o useEffect só será executado uma vez, após a primeira renderização do componente.

Podes mudar nossa funçao handleInputOnChange para utilizar useeffect?

Sim, é possível utilizar o hook useEffect em vez da função handleInputOnChange. A função handleInputOnChange seria transformada em um efeito colateral que é executado sempre que o valor de deliveryNumber for alterado.

Aqui está como ficaria o código:



```javascript
import { useEffect } from 'react';

function MeuComponente() {
  const [deliveryNumber, setDeliveryNumber] = useState('');
  const [entryNumberData, setEntryNumberData] = useState(false);

  useEffect(() => {
    console.log('----DELIVERY: ', deliveryNumber);
    if (deliveryNumber !== '') {
      setEntryNumberData(true);
      console.log(entryNumberData);
    } else {
      setEntryNumberData(false);
    }
  }, [deliveryNumber]);

  // ... o resto do código do componente
}
```


Observe que o código da função handleInputOnChange foi colocado dentro do useEffect. Além disso, adicionei uma lista de dependências como segundo argumento da função, para que o useEffect seja executado sempre que o valor de deliveryNumber for alterado.

Agora, ao invés de usarmos a função handleInputOnChange como uma propriedade de um elemento, nós podemos controlar o efeito colateral diretamente no componente. Isso pode ser útil se você quiser executar alguma lógica sempre que o valor de deliveryNumber for alterado, sem precisar se preocupar com a captura de eventos ou com a definição de propriedades.
E como fica o onchange do input?

Se você estiver utilizando o useEffect em vez da função handleInputOnChange, o evento onChange do input pode ser usado da mesma forma. A única diferença é que, ao invés de chamar a função handleInputOnChange, você precisará atualizar o valor de deliveryNumber diretamente.

Aqui está como ficaria o código completo do componente:

```javascript 
import { useState, useEffect } from 'react';

function MeuComponente() {
  const [deliveryNumber, setDeliveryNumber] = useState('');
  const [entryNumberData, setEntryNumberData] = useState(false);

  useEffect(() => {
    console.log('----DELIVERY: ', deliveryNumber);
    if (deliveryNumber !== '') {
      setEntryNumberData(true);
      console.log(entryNumberData);
    } else {
      setEntryNumberData(false);
    }
  }, [deliveryNumber]);

  return (
    <input
      value={deliveryNumber}
      onChange={({ target: { value } }) => setDeliveryNumber(value)}
    />
  );
}
```
Agora, ao digitar algo no input, o valor de deliveryNumber será atualizado e o useEffect será executado, alterando o valor de entryNumberData e exibindo as mensagens no console.
Me explique o useState, e quais sao as outras alternativas?

O hook useState é uma função do React que permite que você adicione estado aos seus componentes funcionais. Ele retorna um par de valores: o estado atual e uma função para atualizá-lo.

Por exemplo, aqui está como o useState é usado para adicionar o estado count a um componente:

```javascript
import { useState } from 'react';

function MeuComponente() {
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>O valor atual é {count}</p>
      <button onClick={() => setCount(count + 1)}>Incrementar</button>
    </div>
  );
}
```
No exemplo acima, o componente possui o estado count, inicialmente definido como 0, e a função setCount para atualizá-lo. Quando o botão é clicado, a função é chamada para incrementar o valor de count.

O useState é uma alternativa ao uso de classes para criar componentes com estado. Ao invés de criar uma classe e escrever métodos para gerenciar o estado, você pode usar o useState em componentes funcionais para obter o mesmo resultado.

Outras alternativas para gerenciar o estado em componentes do React são o Redux e o Context API. Essas ferramentas são mais avançadas e permitem gerenciar o estado em aplicações maiores, mas requerem mais configuração e podem ser mais complexas de se trabalhar. O useState é uma opção mais simples e fácil de usar, principalmente em aplicações pequenas ou em componentes isolados.
E se fosse emm Context API? como ficaria?

Se você quiser usar o Context API para gerenciar o estado em vez do useState, o código ficaria mais ou menos assim:



```javascript
import { createContext, useContext } from 'react';

// Cria o contexto
const CountContext = createContext();

function MeuComponente() {
  // Consome o contexto
  const [count, setCount] = useContext(CountContext);

  return (
    <div>
      <p>O valor atual é {count}</p>
      <button onClick={() => setCount(count + 1)}>Incrementar</button>
    </div>
  );
}

function App() {
  const [count, setCount] = useState(0);

  return (
    // Fornece o contexto
    <CountContext.Provider value={[count, setCount]}>
      <MeuComponente />
    </CountContext.Provider>
  );
}
```
No código acima, criamos um contexto chamado CountContext e o fornecemos para o componente MeuComponente como um provedor. Em seguida, o componente consome o contexto com useContext e obtém o valor atual e a função para atualizá-lo.

Diferentemente do useState, o Context API permite que você compartilhe o estado entre componentes que estejam em diferentes partes da árvore de componentes, sem precisar passar props manualmente de pai para filho. Isso pode ser útil em aplicações maiores, mas requer mais configuração e pode ser um pouco mais complexo de se trabalhar. O useState é uma opção mais simples e fácil de usar, principalmente em aplicações pequenas ou em componentes isolados.
starambients@gmail.com
E se fosse em Redux, como ficaria?

Se você quiser usar o Redux para gerenciar o estado em vez do useState, o código ficaria mais ou menos assim:


```javascript
import { connect } from 'react-redux';

function MeuComponente(props) {
  const { count, incrementCount } = props;

  return (
    <div>
      <p>O valor atual é {count}</p>
      <button onClick={incrementCount}>Incrementar</button>
    </div>
  );
}

// Mapeia o estado do Redux para as props do componente
const mapStateToProps = (state) => ({
  count: state.count
});

// Mapeia as actions do Redux para as props do componente
const mapDispatchToProps = (dispatch) => ({
  incrementCount: () => dispatch({ type: 'INCREMENT' })
});

export default connect(mapStateToProps, mapDispatchToProps)(MeuComponente);
```
No código acima, usamos o connect do react-redux para mapear o estado e as actions do Redux para as props do componente. Em seguida, passamos o componente como argumento para o connect, que retorna um novo componente enriquecido com as props mapeadas.

O Redux é uma ferramenta poderosa para gerenciar o estado em aplicações maiores, mas requer mais configuração e pode ser mais complexo de se trabalhar. O useState é uma opção mais simples e fácil de usar, principalmente em aplicações pequenas ou em componentes isolados.