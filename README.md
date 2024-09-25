# MediaQueries-POC
Poc de WEB - Media Queries



<img src="https://www.lambdatest.com/blog/wp-content/uploads/2022/07/Banner20CSS20media20queries.png" width="600px" >

# Utilização de Media Queries

 <!--ts-->
 
 * [Print - apenas impressão](#Print - apenas impressão)
 * [Larguras de dispositivos diferentes](#Larguras de dispositivos diferentes)
 * [Disposição dos dispositivos](#Disposição dos dispositivos)
 
 <!--te-->


 ## Print - apenas impressão
 O operador "spread" do JavaScript ( ...) expande um iterável (como uma matriz) em mais elementos.<br>
 Isso nos permite copiar rapidamente todas as partes de um array existente para outro array:
 ~~~javascript
 const numbersOne = [1, 2, 3];
 const numbersTwo = [4, 5, 6];
 const numbersCombined = [...numbersOne, ...numbersTwo];
 ~~~~

 O operador "spread" é frequentemente usado para extrair apenas o que é necessário de uma matriz:
 ~~~javascript
 const numbers = [1, 2, 3, 4, 5, 6];

 const [one, two, ...rest] = numbers;
 ~~~~

 Podemos usar o operador "spread" também com objetos:
 ~~~javascript
 const myVehicle = {
  brand: 'Ford',
  model: 'Mustang',
  color: 'red'
}

const updateMyVehicle = {
  type: 'car',
  year: 2021,
  color: 'yellow'
}

const myUpdatedVehicle = {...myVehicle, ...updateMyVehicle}
 ~~~~
 ## Larguras de dispositivos diferentes
 O método MAP no javascript consegue executar uma funcão diretamente para cada elemento do array

 Por exemplo, imagine que desejamos retornar a raiz quadrada dos números abaixo:
 ~~~javascript
 const numeros = [4, 9, 16, 25]
 ~~~~
 Basta aplicar o método map, indicando dentro do parenteses a função que deseja aplicar para cada valor do array:
 ~~~javascript
 const raizQuadrada = numeros.map(Math.sqrt)
 // raizQuadrada = [2, 3, 4, 5]
 ~~~~

 ## Disposição dos dispositivos
 Este metodo tem por objetivo transformar todo o conteudo de uma Array em apenas um elemento.<br>
 Por exemplo:

 Tendo uma lista de numeros como:
 ~~~javascript
 const Numeros = [1, 2, 3];
 ~~~~

Podemos utilizar o metodo reduce da seguinte maneira:
~~~javascript
const total = Numeros.reduce((total, currentElement) => total + currentElement)
// Total = 6
~~~
sendo,<br>

~~~javascript
const total
~~~

a variavel onde será guardada a array reduzida

~~~javascript
(total, currentElement)
~~~

os parâmetros do metodo

~~~javascript
total + currentElement
~~~ 
o modo como sera reduzido, neste caso somando.
