# Introducción a HTTP y URI

## Comprendiendo Request y Response

Empezamos abriendo nuestro terminal. En el caso de Windows, abriremos PowerShell. Y ejecutaremos la sigueinte línea de comando.

```
curl 'http://randomword.saasbook.info'
```
Inmediatemente, en el terminal se mostrará el siguiente resultado. Y lo guardaremos en un archivo con `> nombreArchivo`.

```
StatusCode        : 200
StatusDescription : OK
Content           : <!DOCTYPE html>
                    <html lang="en">
                      <head>
                        <meta charset="utf-8">
                        <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.0-beta1/dist/css/bootstrap.min.css"
                    rel="stylesheet" integrity="sha384-g...
RawContent        : HTTP/1.1 200 OK
                    Connection: keep-alive
                    X-Xss-Protection: 1; mode=block
                    X-Content-Type-Options: nosniff
                    X-Frame-Options: SAMEORIGIN
                    Content-Length: 482
                    Content-Type: text/html;charset=utf-8
                    Dat...
Forms             : {}
Headers           : {[Connection, keep-alive], [X-Xss-Protection, 1; mode=block], [X-Content-Type-Options, nosniff],
                    [X-Frame-Options, SAMEORIGIN]...}
Images            : {@{innerHTML=; innerText=; outerHTML=<IMG src="esaas.png">; outerText=; tagName=IMG;
                    src=esaas.png}}
InputFields       : {}
Links             : {}
ParsedHtml        : mshtml.HTMLDocumentClass
RawContentLength  : 482
```
Por otro lado, lo volveremos a guardar, pero esta vez en formato HTML. Se mostrará el siguiente resultado al abrir el archivo.
```
StatusCode : 200 StatusDescription : OK Content : ; outerText=; tagName=IMG; src=esaas.png}} InputFields : {} Links : {} ParsedHtml : mshtml.HTMLDocumentClass RawContentLength : 481 
```

**Pregunta:** ¿Cuáles son las dos diferencias principales que has visto anteriormente y lo que ves en un navegador web 'normal'? ¿Qué explica estas diferencias?

En el archivo común se muestra a detalle la descripción a una respuesta HTTP, incluyendo datos técnicos y metadatos, pero no se muestra la página web de manera completa y funcional como en el archivo HTML. Esta diferencia se explica uno solo muestra el contenido, y el otro, lo interpreta.

Ahora veremos cómo cree el servidor que ve una solicitud. Ejecutamos el siguiente comando.

```
nc -l 8081
```