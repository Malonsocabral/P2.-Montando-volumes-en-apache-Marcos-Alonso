# P2.-Montando-volumes-en-apache-Marcos-Alonso
## Comproba que a tes a imaxe httpd

Para conprobar que temos esta imaxe, debemos utilizar o comando `docker images` xa que lista todas as imaxes do noso sistema.

## Crea un contenedor de nome 'asir_httpd'.Mapea o porto 80 do contenedor có 8080 da túa máquina.Utiliza bind mount para que o directorio do apache2 'htdocs' estea montado nun directorio da túa elección. Utiliza -v "$PWD"/htdocs:/usr/local/apache2/htdocs/.
Para crear o contenedor co nome *asir_httpd* mapeando o porto 80 do contenedor e o -v coa ruta dada.Lancei o seguinte comando: `docker run --name asir_httpd -p 8080:80 -v /home/postgres/server:/usr/local/apache2/htdocs httpd`
>[!NOTE]
>Esta imaxe conten o contido da carpeta server do meu directorio principal *(/home/postgres/server)*

<!--
## Mapea o porto 80 do contenedor có 8080 da túa máquina.

## Utiliza bind mount para que o directorio do apache2 'htdocs' estea montado nun directorio da túa elección. 

   ### Utiliza -v "$PWD"/htdocs:/usr/local/apache2/htdocs/
-->

## Mostra unha páxina html aloxada no apache2 dende o teu navegador.
Na imaxe de antes xa contaba cun html xerado por mi polo que ao lanzar o contenedor xa empezou unha paxina html.

## Crea un contenedor 'asir_web1' que use este mesmo directorio para 'htdocs' e o puerto 8000

## Crea outro contenedor 'asir_web2' có el mesmo directorio e otro puerto, como o 8090.

## Comproba que los dous servidores mostran a mesma páxina

Fai a entrega describindo os pasos usados con comandos no readme dun proxecto público en git, adxunta no entregable o enlace. 
