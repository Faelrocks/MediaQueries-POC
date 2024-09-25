# MediaQueries-POC
Poc de WEB - Media Queries



<img src="https://github.com/user-attachments/assets/7c8c6b73-9dc0-43da-9847-adf15889f72d" width="600px" >

# Metodos de Array em JS

 <!--ts-->
 
 * [Spread](#Spread)
 * [Map](#Map)
 * [Reduce](#Reduce)
 * [Filter](#Filter)
 * [Sort](#Sort)
 
 <!--te-->


 ## Spread
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
 ## Map
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

 ## Reduce
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



 ## Filter
 O método filter basicamente filtra um array respeitando as condições indicadas pelo usuário, retornando os resultados em um novo array.

 Por exemplo, considere o array abaixo que contenha as idades de diversas pessoas:
 ~~~javascript
 const idades = [5, 12, 15, 17, 18, 19, 25, 32, 33, 54];
 ~~~

 Então, queremos filtrar apenas as idades que podem dirigir veícuos automotores no Brasil, ou seja, igual ou maiores de 18 anos, teriamos a seguinte função:
 ~~~javascript
 function habilitacao(idades) {
	return idades >= 18;
 }
 ~~~
 Para retornar um novo array já com os resultados, basta utilizar o método 'filter', indicando dentro do parenteses a condição ou função que deseja filtrar :
 ~~~javascript
 const permitidos = idades.filter(habilitacao);
 //permitidos = [ 18, 19, 25, 32, 33, 54 ]
 ~~~

 Importante ressaltar que o método não funciona para valores vazios (null), e também não altera o array original

 ## Sort
 O método sort tem por objetivo organizar os elementos de uma array seguindo uma logica informada pelo desenvolvedor. <br>
 <br>
 
Para demonstrar o metodo vamos organizar uma lista de vendas de uma empresa de varejo dada pelo seguinte array:

~~~javascript
const produtos = [
	{produto: 'TV', nVendido: 600},
	{produto: 'Batedeira', nVendido: 900},
	{produto: 'Geladeira', nVendido: 300},
	{produto: 'Forno', nVendido: 200},
];
~~~

Podemos ver que a array possui a quantidade de vendas de determinados produtos sem uma sequencia logica aparente.<br>
Para mudar isso podemos usar o método sort da seguinte maneira:
~~~javascript
const Vendas = produtos.sort((a, b) => b.nVendido - a.nVendido);
~~~
neste caso o método ira retornar a array desta maneira:

~~~javascript
const produtos = [
	{produto: 'Batedeira', nVendido: 900},
	{produto: 'TV', nVendido: 600},
	{produto: 'Geladeira', nVendido: 300},
	{produto: 'Forno', nVendido: 200},
];
~~~

podemos perceber que o método organizou a array de maneira decrescente por conta da logica de organização que foi dada
~~~javascript
((a, b) => b.nVendido - a.nVendido);
~~~
Podemos organizar arrays de maneiras diferentes ao passo que alteramos sua logica de organização.<br>
Podemos por exemplo organizar o array de maneira crescente da seguinte maneira

~~~javascript
const Vendas = produtos.sort((a, b) => a.nVendido - b.nVendido);
~~~
o retorno desta logica de organização será:
~~~javascript
const produtos = [
{produto: 'Forno', nVendido: 200},
{produto: 'Geladeira', nVendido: 300},
{produto: 'TV', nVendido: 600},
{produto: 'Batedeira', nVendido: 900},
];
~~~
