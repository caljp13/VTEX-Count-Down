#VTEX - Count Down
>*Extensões da plataforma VTEX são plugins criados por desenvolvedores de interface ou pelo VTEX Lab (Laboratório de Inovações da VTEX) que podem ser inseridas em sua loja. Existem extensões gratuitas com código aberto -  Open Source - e extensões pagas.  Indicamos que a instalação seja realizada pelos profissionais e empresas certificados pela VTEX. Vale ressaltar que qualquer profissional de CSS, JavaScript e HTML pode também executar esta tarefa.*

----------
###Atenção
> Esta extensão é mantida por [Quatro Digital](http://www.quatrodigital.com.br) e não possui suporte gratuito.  
> O código fonte deste componente não pode ser vendido ou comercializado, ele esta livre para uso comercial mas só podem haver cobranças com relação à mão de obra necessária a sua instalação e não por sua utilização.  
> O correto funcionamento deste script não é de responsabilidade de seu desenvolvedor, mantenedor ou constribuidores.  
> Caso queira contribuir com o desenvolvimento fique a vontade para fazer um `Fork` e posteriormente um `pull request`.

**O uso desta extensão esta sob as regras da lincença: [MIT](http://pt.wikipedia.org/wiki/Licen%C3%A7a_MIT)**

----------

Veja este componente na [VTEX Store](http://conversionstore.com.br/)

##Instalação
Faça o upload para o "Gerenciador do portal" no "Vtex Admin" dos seguintes arquivos:
* vtex-countdown.min.js

Crie uma promoção no admin onde o nome contenha a data limite para adquirir o produto, nesse formato:
`
NOMEdaPROMOCAO |DD/MM/AAAA HH:MM
ex.: "Tempo Regressivo |03/02/2012 22:10"
`

Faça a chamada do arquivo javascript na página:

```html
<script type="text/javascript" src="/arquivos/vtex-countdown.min.js"></script>
```

Execute o plugin:

```javascript
$(".skuWrap").vtexCountdown();
```

Configurações do plugin (atualizada em: 13/08/2013)
```javascript
$(".skuWrap").vtexCountdown({
	element : "p[class*='|']", // Elemento em que esta a promoção. Normalmente o sistema gera um "<p>"
	separator:"|", // Caracter que separa o nome da promoção de sua data limite no título
	dateSeparator:"/", // Separador de data, usado entre o número de dias, mês e ano
	hourSeparator:":", // Separador de horas
	outputFormat:1, // [1] Dias, hrs, min., seg. - [2] hrs, min., seg. // Modelo de impressão do contador
	// HTML onde será montado o contador
	htmlFormat : '<span class="days qd-cp-timeinfo">%days% <span class="vtex-cd_p qd-cp-text">dias</span><span class="vtex-cd_s qd-cp-text">dias</span> </span><span class="hours qd-cp-timeinfo">%hours% <span class="vtex-cd_p qd-cp-text">horas</span><span class="vtex-cd_s qd-cp-text">hora</span> </span><span class="minutes qd-cp-timeinfo">%minutes% <span class="vtex-cd_p qd-cp-text">minutos</span><span class="vtex-cd_s qd-cp-text">minuto</span> </span><span class="seconds qd-cp-timeinfo">%seconds% <span class="vtex-cd_p qd-cp-text">segundos</span><span class="vtex-cd_s qd-cp-text">segundo</span> </span>',
	updatInterval:1000, // Intervalo de atualização do contador na tela em milesegundos. 1000 milisegundos = 1 segundo
	callback:function(){}, // Callback após renderizar o contador.
	updateCallback:function(){}, // Callback após cada atualização
	removeDateText : true, // Se "true" irá remover a data do nome da promoção, exibindo ao usuário apenas o título dela
	displayElement : null // Opção para definir um seletor ou um elemento jQuery no qual será exibido o contador
});
```