# Calculadora JavaScript  

Calculadora desenvolvida como exemplo do Curso Completo de JavaScript na Udemy.com.  
Este MD será usado apenas para anotações ao decorrer do projeto.

### Projeto
![Calculadora](https://firebasestorage.googleapis.com/v0/b/hcode-com-br.appspot.com/o/calculadora-hcode.jpg?alt=media&token=5406aa3f-b965-401c-9b4e-654609c78b33)

## Pequena revisão
>**Funções**
- São trechos de códigos que podem ser reutilizados.  

>**Classes**
- Agrupam atributos e métodos no mesmo lugar.  

>**Return**  
- Encerra a função e retorna um valor.  

>**eval()**  
- Para cálculos (interpreta variável contendo +, -, *), string  

>**Funções Anônimas**
- Não tem um nome e podem ser chamadas logo após criadas.  

>**Arrow Function**
- Consegue compartilhar coisas de fora da função para a função.  

>**Callback**
- Função de retorno como parâmetro após uma ação.  

>**DOM**  
- Document Object Model - A estrutura como o HTML é formado.  

>**window**
- Janela  

>**document**
- Site  

>**TimeStamp**  
- Quantidade de segundos desde 01/01/1970 até hoje. No JS ele estará em milissegundos.  

>**new Date()**  
- Instância a data atual.  

>**toLocaleDateString(“pt-BR”)**  
- Converte data para padrão BR.  
>**toLocaleTimeString('pt-BR')**  
- Formata a hora.
**variavel.getDate();** - Retorna o dia da variável.  
**variavel.getMonth();** - Retorna o mês da variável.  
**variaval.getFullYear();** - Retorna o ano da variável.  
```js
variavel.toLocaleDateString('pt-BR', (month:'long'))

long = completo
short = abreviado
```
>**forEach()**  
- Laço para percorrer Array.  

# Calculadora

**CSS incorporado** - CSS é aplicado diretamente no HTML.  
**SVG** - Linguagem XML para descrever desenhos em vetor.  
<br>
**POO Benefícios**:
>Praticidade, Reutilização e Abstração.

**Instância** - É quando um objeto representa uma classe.  
**Encapsulamento** - É uma forma de controlar quem tem acesso a um atributo ou um método.  
**Public** -  Todos acessam.  
**Protected** -  Apenas atributos da mesma classe e classe pai.  
**Private** - Somente atributos e métodos da mesma classe.  

```js
class Calc Controller {
   constructor(){
       this._displayCal = '0';
       this._dataAtual;
   }
}
```
>A cima uma convenção JS (o uso do _), para dizer que esse atributo ou método é privado.

**MVC:**  
Model **|** View **|** Controller  
<br>
Model - Dados  
View - Interface  
Controller - O que pode ou não acontecer  

## 1 - C04 - Manipulando o DOM

>É interessante programar sempre em inglês, afinal as palavras reservadas são em inglês, e o código fica legível para qualquer lugar do mundo.  

**Dica no VScode**: Selecionar uma palavra e apertar Ctrl + D ele irá selecionar todas partes do código que tem a mesma palavra.  
<br>
**BOM** - Vem de "Browser Object Model. Seria a janela. "window". (barra de endereços, maximizar ou minimizar a janela, etc).  
>Temo que ter cuidado ao interagir com o DOM para o site/aplicação não ficar tão pesada, afinal estamos mexendo com algo que já foi renderizado para o usuário.  
<br>

Usando o mouse, teclado ou outro, criamos **Eventos** - Que são ações disparadas na aplicação. (passou um determinado tempo, apertou uma tecla, clicou em algum lugar, etc. Tudo em seu documento).  
<br>
**What's "Document"?** - É o site.  
**close()** -  É um método que fecha a janela. ou seja, será usada após o window: **window.close();**  
**document.querySelector** - Seleciona elementos por meio de **seletores CSS3**.

```js
initialize() {
        let displayCalcEl = document.querySelector ('#display');
        let dateEl = document.querySelector ('#data');
        let timeEl = document.querySelector ('#hora');
    }
```
>O javascript agora entende esses três caras.

```js
        displayCalcEl.innerHTML = "4567";
        dateEl.innerHTML = "09/08/2020";
        timeEl.innerHTML = "00:00";
```

>o .innerHTML serve parar  **mudar** o conteúdo em determinado elemento, no caso a cima um elemento que está associado a uma variável.

## 2 - C05 - Data e Hora  

**Refatorar** - Melhorar ou revazar o código, otimizando o mesmo.  
<br>

##### Definindo um intervalo de repetição para a hora:  

```js
setInterval (() => {

            this.displayDate = this.currentDate.toLocaleDateString(this._locale);
            this.displayTime = this.currentDate.toLocaleTimeString(this._locale);

        }, 1000)
    }
```
>O "1000" representa os milissegundos para repetir o trecho de código.  

**PS:** Foi usado o this._locale para guardar a localização.  
**PS²:** Note que foi usado uma Arrow Function.  
<br>
##### Parando o Intervalo (não necessário para o projeto) 

```js
let interval = setInterval (() => {

            this.displayDate = this.currentDate.toLocaleDateString(this._locale);
            this.displayTime = this.currentDate.toLocaleTimeString(this._locale);

        }, 1000);

        setTimeout(() => {

            clearInterval(interval);
        
        }, 10000);
```

>Depois de 10 segundos, o setInterval irá parar  

**PS:** O set Interval foi associado a uma váriavel.  
<br>

##### Informações demoram 1000 milissegundos para aparecer

Isso acontece pois o setInterval espera 1 segundo para rodar a primeira vez.  
Para concertar isso definimos as informações antes do setInterval *(Já que iremos usar mais de uma vez, transformaremos em um método.)*  

```js
initialize() {

        this.setDisplayDateTime();

        setInterval (() => {

            this.setDisplayDateTime();

        }, 1000);

    }
```

<br>

##### Formatando mais uma vez a data no display  

>Note a manipulação em cada parte da data :)  

```js
setDisplayDateTime() {
        this.displayDate = this.currentDate.toLocaleDateString(this._locale, {
            day: '2-digit',
            month: 'long',
            year: 'numeric'
        });
        this.displayTime = this.currentDate.toLocaleTimeString(this._locale);
    }
```

## 3 - C06 - querrySelector

```js
    document.querySelector('#buttons > g, #parts > g');
```  
>Trará apenas o primeiro elemento possível.  

```js
    document.querySelectorAll('#buttons > g, #parts > g');
```  
>Trará **todos** os elementos possíveis.  

## 4 - C07 - Adicionando Evento Click

O JavaScript reage a eventos de click, teclado, tempo e interações do próprio usuário, e vários outros.  
Podemos adicionar várias escutas de eventos e tratar depois.

```js
    initButtonsEvents() {

            let buttons = document.querySelectorAll('#buttons > g, #parts > g');
            buttons.forEach((btn,index) => {
                
                btn.addEventListener('click', e=> {

                    console.log(btn.className.baseVal.replace('btn-', ''));
        
                });
        
            })
        }
```  
>replace foi usado para retirar parte do nome da **classe** dos elementos.

## 5 - C08 - Aplicando vários Eventos usando split()

As vezes precisamos de vários eventos fazendo a mesma função, então não é interessante copiar os mesmos códigos.  
Por exemplo, nesta situação se o usuário sem querer clicar e puxar o botão do número, não será considerado como um clique (imagine em um disposito móvel).  

>Será necessário transformar uma string (contendo os eventos), em um Array.  
>E é claro, criar um evento próprio, já que o addEventListener não capta mais de um evento.  

>Repare que o **split()** necessita de um parâmetro para saber como irá divitir o array, nesse caso o espaço foi usado. 


```js
    addEventListenerAll (element, events, fn ) {
            
            events.split(' ').forEach(event => {

                element.addEventListener(event, fn, false);

            });

        }
```  

>Note que element a cima, se refere a btn abaixo. 'click drag mouseover' *(esse ultimo não usado no projeto)* se refere aos eventos a cima.

```js
    initButtonsEvents() {

        let buttons = document.querySelectorAll('#buttons > g, #parts > g');
        buttons.forEach((btn,index) => {
            
            this.addEventListenerAll(btn, 'click drag mouseover', e => {

                console.log(btn.className.baseVal.replace('btn-', ''));
    
            });
    
        });
    }
```

## 6 - C09 - Switch  

É usado quando se sabe valores exatos para decidir um fluxo de código.  

##### Adicionando/Removendo elementos no final de Arrays
```js
    operation.push(value);  //Value será adicionado no fim do Array
    
    operation.pop();        //Remove o ultimo elemento do Array
```  

> Ou seja, o **pop** será utilizado no CE, afinal, essa tecla limpa apenas a ultima entrada da calculadora:  

```js
//Criando o método
    clearEntry() {
        
        this._operation.pop();

    }
//_____________________________________________________
//No Switch
    switch(value) {
        
        case 'ac':
            this.clearAll();
            break;
//...
```

##### Zerando o display

> Basta apenas  