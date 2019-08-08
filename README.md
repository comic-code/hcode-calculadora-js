# Calculadora JavaScript

[![Hcode Treinamentos](https://www.hcode.com.br/res/img/hcode-200x100.png)](https://www.hcode.com.br)

Calculadora desenvolvida como exemplo do Curso Completo de JavaScript na Udemy.com.

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
