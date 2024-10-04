# P2_Montando volumes en apache_Marcos Alonso Cabral_ASIR2
Antes de nada, vou deixar un enlace a un documento de google no que podese observar mediante imaxes o proceso: [LINK_DOCUMENTO](https://docs.google.com/document/d/1KCy6HQL_wxuUOtnaGHkqYr84U7D4Jz7HQ5BeaPTw15o/edit?usp=sharing).
## Comproba que a tes a imaxe httpd

Para conprobar que temos esta imaxe, debemos utilizar o comando `docker images` xa que lista todas as imaxes do noso sistema.

## Crea un contenedor de nome 'asir_httpd'.
Para crear o contenedor co nome *asir_httpd*  utilizaremos o comando `docker run --name <nome do contenedor> <imaxe>` : No meu caso utilicei o "Run" xa que asi o lanzo xa, pero se queremos soo crealo debemos utilizar o comando pero cambiando el run por *create*

## Mapea o porto 80 do contenedor có 8080 da túa máquina.Utiliza bind mount para que o directorio do apache2 'htdocs' estea montado nun directorio da túa elección. Utiliza -v "$PWD"/htdocs:/usr/local/apache2/htdocs/.




Para crear o contenedor co nome *asir_httpd* como fixemos no anterior punto e mapear o porto 80 do contenedor e o -v coa ruta dada.Lancei o seguinte comando que e un conxunto de comandos '*`-p 8080:80`*' para mapear o porto 80 e logo co comando seguinte montamos o directorio htdocs do servidor apache: `-v "<Directorio_montar>:/usr/local/apache2/htdocs/ <imaxe>`, e para finalizar, o conxunto dos anteriores comandos é o seguinte: `docker run --name asir_httpd -p 8080:80 -v /home/postgres/server:/usr/local/apache2/htdocs httpd`
>[!NOTE]
>Esta imaxe conten o contido da carpeta server do meu directorio principal *(/home/postgres/server)*

## Mostra unha páxina html aloxada no apache2 dende o teu navegador.
Na imaxe de antes xa contaba cun html xerado por mi polo que ao lanzar o contenedor xa empezou unha paxina html no porto 8080 e para poder acceder a ella debemos poner `localhost:8080`.


## Crea un contenedor 'asir_web1' que use este mesmo directorio para 'htdocs' e o puerto 8000

Para facer este paso, podemos itulizar o comando explicado no punto 3 pero cambiando os parametros. E unha vez feito, o comando quedaria tal que asi : `docker run -d --name asir_web1 -p 8000:80 -v /home/postgres/server/htdocs:/usr/local/apache2/htdocs/ httpd `
>[!NOTE]
>Podemos ver que se ha creado correctamente en las imagenes del link de google que proporcione en la primera linea de este trabajo.
>[LINK_DOCUMENTO](https://docs.google.com/document/d/1KCy6HQL_wxuUOtnaGHkqYr84U7D4Jz7HQ5BeaPTw15o/edit?usp=sharing).

## Crea outro contenedor 'asir_web2' có el mesmo directorio e otro puerto, como o 8090.
Para crear outro contenedor e tan sinxelo como copiar o link de antes , so cambiandolle o nome de *asir_web1* a *asir_web2* e o porto de *8000* a *8090*.
O comando quedaria tal que asi : `docker run -d --name asir_web2 -p 8090:80 -v /home/postgres/server/htdocs:/usr/local/apache2/htdocs/ httpd `
## Comproba que los dous servidores mostran a mesma páxina
Para comprobar que os dous servidores mostran a mesma paxina temos que executar estes dos comandos de forma que non se peche a paxina web *(podese facer dende VS ou abrindo dous terminales, una para cada comando)*.Logo abrimos o navegador e nunha ventá poñemos `localhost:8000` (*para asir_web1*) e noutra ventá `localhost:8090` (*para asir_web2*).
>[!NOTE]
>O resultado podese ver no link de google do comenzo
> [LINK_DOCUMENTO](https://docs.google.com/document/d/1KCy6HQL_wxuUOtnaGHkqYr84U7D4Jz7HQ5BeaPTw15o/edit?usp=sharing).
