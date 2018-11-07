---
layout: post
title: API Ruby Google Geo - Exemplo
date: 2007-02-13 12:27:27.000000000 -03:00
type: post
parent_id: '0'
published: true
password: ''
status: publish
categories:
- Ruby
tags: [ruby,linux]
meta: {}
author:
  login: tassiovirginio
  email: tassiovirginio@gmail.com
  display_name: Tássio Virgínio
  first_name: Tássio
  last_name: Virgínio
---
<p>Lá estava eu navegando pela internet novamente, comecei a ficar cansado e fui direto na fonte dos pacotes disponiveis no ruby =&gt; <a href="http://rubyforge.vm.bytemark.co.uk/gems/">http://rubyforge.vm.bytemark.co.uk/gems/</a> , como sou curioso procurei “F3 do Firefox” por Google :P , achei uma api a <a href="http://dev.robotcoop.com/Libraries/google-geocode/">google-geocode</a> blz… vamos fazer novamente, fazer uma aplicação Ruby on Rails Simples !</p>

Ai vai o passo-a-passo novamente:
1. Vamos instalar a api:<br>
``` sh
gem install google-geocode
```
2. Iniciamos um projeto:<br>
``` sh
rails googlegeo
```
3. Criamos Um Controller:<br>

  ``` ruby
  class GooglegeoController < ApplicationController
    require 'google_geocode'
    
    def index
    end

    def localizar
      gg = GoogleGeocode.new 'googlegeokey'
      @location = gg.locate params[:localizar]["texto"]
    end
  end

  ```
4. Criamos os views RHTML: 

**index.rhtml**

``` rhtml
<br><br><br>
<center>
<img src='http://www.google.com/intl/en_ALL/images/maps_results_logo.gif' />
<br>
<br>
<%= start_form_tag :action => 'localizar' %>
<%= text_field 'localizar','texto' %>
<%= submit_tag "Localizar" %>
<%= end_form_tag %>
</center>
```
**localizar.rhtml**

``` rhtml
<html>
<head>
<meta content='text/html; charset=utf-8' http-equiv='content-type' />
<title>Google Maps JavaScript API Example</title>
<script type='text/javascript' src='http://maps.google.com/maps?file=api&v=2&key=googlegeokey'></script>
<script type='text/javascript'>
  //<![CDATA[
    function load() {
      if (GBrowserIsCompatible()) {
        var map = new GMap2(document.getElementById("map"));
        map.setCenter(new GLatLng(<%=@location.coordinates[0]%>, <%=@location.coordinates[1]%>), 10);
      }
    }
  //]]>
</script>
</head>
<body>
  <img src='http://www.google.com/intl/en_ALL/images/maps_results_logo.gif' />
  <br>
  <div id='map' style='width: 500px; height: 300px'></div>
</body>
</html>
```

<p><span class="caps">OBS</span>: googlegeokey =&gt; tem que pegar no site do google   =&gt; <a href="http://www.google.com/maps/">http://www.google.com/maps/</a></p>
<p>Esse sistema funciona da seguinte maneira, primeiro aparece uma pagina com uma caixa de texto e um botão, ali vc coloca o nome do pais, cidade ou estado… ai na pagina seguinte é mostrado o mapa do local. Não sei se ficou bem feito ! Se alguem puder melhorar o codigo fique avontade ! Até mais pessoal !</p>
