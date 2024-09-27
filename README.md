# MediaQueries-POC
Poc de WEB - Media Queries



<img src="https://www.lambdatest.com/blog/wp-content/uploads/2022/07/Banner20CSS20media20queries.png" width="600px" >

# Utilização de Media Queries

 <!--ts-->
 
 * [Print - apenas impressão](#Print)
 * [Larguras de dispositivos diferentes](#Larguras)
 * [Disposição de Dispositivos](#Disposição_de_Dispositivos)
 
 <!--te-->


 ## Print
 O Media Print tem por função adptar o site para que facilite a sua impressão.

 podemos observar o nosso site modelo abaixo, nele foi simulado o boletim de um aluno do Mackenzie.
 
![Captura de tela 2024-09-27 134159](https://github.com/user-attachments/assets/806acfcc-8125-41de-8bac-8f3237dd089f)

O site possui o seguinte css:

~~~css
h1{
    text-align: center;
    color: white;
}

body{
    background-color: rgb(234, 13, 43);
}

p{
    color: white;
}

img{
    height: 200px;
}

#foto{
    border: white solid 10px;
}

#fotos{
    display: flex;
    flex-direction: row;
    justify-content:space-around;
    width: 100%;
    margin-bottom: 8%;
}


#main{
    display: flex;
    justify-content: space-evenly;
    width: 100%;
}

#main > div{
    width: 50%;
    align-content: center;
    text-align: center;

}

#dados{
    display: flex;
    flex-direction: column;
}

#notas{
    display: flex;
    justify-content: space-evenly;
    margin-top: 10%;
}

.rodape{
    display: none;
}

~~~~

Podemos perceber que alguns fatores no site dificultam a sua impressão e levam a um consumo exagerado de tinta, por exemplo, a cor de vermelha de fundo e as imagens presentes no site.

Para auxiliar o usuario podemos utilizar o @media print para realizar algumas alterações apenas quando o usuario for realizar a impressão da pagina.

~~~css
@media print {
    
    body{
        background-color: white;
    }
    
    p{
        color:black
    }

    h1{
        color:black;
    }

    img{
        display: none;
    }

    #notas{
        flex-direction: column;
        margin-top: 0px;
    }

    .rodape{
        display:flex;
        width: 100%;
        justify-content: center;
        margin-top: 5%;
    }
}

~~~~
Com essa media querie quando o usuario utilizar o atalho CTRL + P tera o seguinte resultado pra impressão:

![Captura de tela 2024-09-27 134233](https://github.com/user-attachments/assets/ef98c1f2-2a14-453c-b914-413a688452c5)

Podemos observar que as imagens foram removidas da pagina, a cor de fundo foi alterada para branco, foi alterada a cor da fonte de texto, foi reformatada a disposição de dados e adicionamos o nome da universidade ao final do documento facilitando assim a impressão e reduzindo o consumo de tinta pela impressora.




 
 ## Larguras
 A principal função da Media Querie é adequar o layout do site para dispositivos dos mais variados tamanhos, chamamos isso de "responsividade".

 Atualmente, os desenvolvedores projetam sites levando em conta três tipos principais de dispositivos

 * Desktops e Notebooks
 * Tablets
 * Celulares

 Por exemplo, imagine que temos um site que demonstra o portifólio de um programador front-end, em sua versão Desktop/Notebook, ele ficaria assim:

 <img src="/portifolio-desktop.png" width="600px" >

 Pelo código CSS, não é preciso utilizar a Media Querie em um primeiro momento, uma vez que o site foi desenvolvido primeiramente para dispositivos Desktop/Notebook

 ~~~css
 @import url('https://fonts.googleapis.com/css2?family=Krona+One&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Montserrat:ital,wght@0,100..900;1,100..900&display=swap');

:root {
    --cor-primaria: #000000;
    --cor-secundaria: #F6F6F6;
    --cor-terciaria: #22D4FD;
    --cor-hover: #272727;

    --fonte-primaria: "Krona One", sans-serif;
    --fonte-secundaria: "Montserrat", sans-serif;
}

* {
    margin: 0;
    padding: 0;
}

body {
    box-sizing: border-box;
    background-color: var(--cor-primaria);
    color: var(--cor-secundaria);
}

.cabecalho {
    padding: 2% 0% 0% 15%; 
}

.cabecalho__menu {
    display: flex;
    gap: 80px;
}

.cabecalho__menu__link {
    font-family: var(--fonte-secundaria);
    font-size: 1.5rem;
    font-weight: 600;
    color: var(--cor-terciaria);   
    text-decoration: none;
}

.apresentacao {
    padding: 5% 15%;
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 82px;
}

.apresentacao__conteudo {
    width: 50%;
    display: flex;
    flex-direction: column;
    gap: 40px;
}

.apresentacao__conteudo__titulo {
    font-size: 2.25rem;
    font-family: var(--fonte-primaria);
}

.titulo-destaque {
    color: var(--cor-terciaria);
}

.apresentacao__conteudo__texto {
    font-size: 1.5rem;
    font-family: var(--fonte-secundaria);
    font-weight: 400;
    font-size: 1.5rem;
}

.apresentacao__links {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: center;
    gap: 32px;
}

.apresentacao__links__subtitulo {
    font-family: var(--fonte-primaria);
    font-weight: 400;
}

.apresentacao__links__navegacao {
    display: flex;
    justify-content: center;
    gap: 16px;
    border: 2px solid var(--cor-terciaria);
    color: var(--cor-secundaria);
    font-family: var(--fonte-secundaria);
    font-weight: 600;
    text-align: center;
    width: 50%;
    padding: 21.5px 0;
    border-radius: 8px;
    font-size: 1.5rem;
    text-decoration: none;

}

.apresentacao__links__navegacao:hover {
    background-color: var(--cor-hover);
}

.apresentacao__imagem {
    width: 50%;
    border-radius: 15px;
}

.rodape{
    color: var(--cor-primaria);
    background-color: var(--cor-terciaria);
    padding: 24px;
    text-align: center;
    font-family: var(--fonte-secundaria);
    font-size: 1.5rem;
    font-weight: 400;
}
 ~~~~
 
Entretanto, quando alteramos a resolução do dipositivo para dimensões nativas de um iPad Mini ou de um iPhone 14 Pro Max, vemos que o site não fica bem legível, com palavras atravessando containers e mal dimensionamento.<br>
 
  *iPad Mini <br>
  <img src="/portifolio-ipad-sem-MQ.png" width="320px.png" >

  *iPhone 14 Pro Max <br>
  <img src="/portifolio-iphon-sem-MQ.png" width="320px.png" >

 Para resolver este problema, utilizamos a Media Querie. <br>
 Através dela conseguimos estabelecer quais propriedades serão consideradas até uma dimensão máxima, mínima ou exata.<br>
 
 Que tal ajustarmos o dimensionamento do nosso portifólio para o iPad mini? repare na figura acima que suas dimensões são 768 x 1024.<br>
 Neste caso, podemos parametrizar para que os valores <b>dentro</b> da Media Querie sejam validos até a resolução 1200px:<br>
 
 ~~~css
 @media (max-width: 1200px) { }
 ~~~~

 Depois, basta realizar as altracões desejadas.<br>
 Em nosso caso, realizei ajustes no cabeçalho e na apresentação do conteúdo<br>

 ~~~css
  @media (max-width: 1200px) {
    .cabecalho {
        padding: 10%;
    }

    .cabecalho__menu {
        justify-content: center;
    }

    .apresentacao {
        flex-direction: column-reverse;
        padding: 5%;        
    }

    .apresentacao__conteudo {
        width: auto;
    }
}
 ~~~~
 Veja o resultado, bem melhor, não?<br>
   *iPad Mini <br>
  <img src="/portifolio-ipad-com-MQ.png" width="320px.png" >

 Entretanto, estes ajuste ainda não ficaram perfeitos para usuários de smartphones, veja:<br>
   *iPhone 14 Pro Max <br>
  <img src="/portifolio-iphon-sem-MQ.png" width="320px.png" >

 Podmos inserir outra Media Querie abaixo da feita anteriormente, desta vez parametrizado para a resolução máxima para 768px:<br>
 ~~~css
 @media (max-width: 768px) {
    .cabecalho {
        padding: 10%;
    }

    .cabecalho__menu {
        justify-content: center;
    }

    .apresentacao {
        flex-direction: column-reverse;
        padding: 10%;        
    }

    .apresentacao__conteudo {
        width: 100%;
        gap: 20px;
    }

    .apresentacao__conteudo__titulo {
        font-size: 1.25rem;
        font-family: var(--fonte-primaria);
        text-align: center;
    }

    .apresentacao__conteudo__texto {
        font-size: 1.0rem;
        font-family: var(--fonte-secundaria);
        font-weight: 400;
        text-align: center;
    }

    .apresentacao__links__subtitulo {
        font-size: 1.25rem;
        font-family: var(--fonte-primaria);
        text-align: center;
    }

    .rodape {
        font-size: 1.0rem;
    }
 }
 ~~~~
 Como resultado, temos os textos e foto dimensionados adequadamente aos usuários de Smartphones:<br>
   *iPhone 14 Pro Max <br>
 <img src="/portifolio-iphon-com-MQ.png" width="320px.png" >

 ## Disposição de Dispositivos
 O recurso de mídia CSS de orientação pode ser usado para testar a orientação da janela de visualização.

 Valores de palavras-chave:

 Retrato: <br>
 A janela de visualização está na orientação retrato, ou seja, a altura é maior ou igual à largura.

~~~~css
@media screen and (orientation: portrait) {
    body {
        background-color: #e0f7fa;
    }

    h1 {
        font-size: 2.5em;
        color: #00796b;
    }

    p {
        font-size: 1.2em;
        color: #004d40;
    }
}
~~~~
<img src="/Imagens Dispositivos/Portrait.jpeg">
 Paisagem: <br>
 A janela de visualização está na orientação paisagem, ou seja, a largura é maior que a altura.

 ~~~~css
@media screen and (orientation: landscape) {
    body {
        background-color: #ffe0b2;
    }

    h1 {
        font-size: 3em;
        color: #e65100;
    }

    p {
        font-size: 1.5em;
        color: #bf360c;
    }
}
~~~~
<img src="/Imagens Dispositivos/Landscape.jpeg">
 
