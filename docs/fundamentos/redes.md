---
sidebar_label: 'Redes'
tags: [nivel 100, redes]
---
import ReactPlayer from 'react-player'

# 🕸️ Introducción a las redes
En términos simples, las redes permiten que todos los dispositivos puedan conectarse entre sí y comunicarse a través del envío y recepción de datos.
No necesariamente deben estar conectadas a internet para que puedan comunicarse, internet es un ejemplo de red, la mas grande.

Otro ejemplo de red, pequeña, es cuando conectas dos equipos celulares para transmitir datos por medio de NFC, Bluetooh, Airdrop, o alguna característica similar, eso es una Red de Area Personal tambien conocida como PAN (Personal Area Network).

Un ejemplo de red de área local o Local Area Network (LAN) son computadoras conectadas a una impresora sea por cable o de manera inalámbrica.

Ahora, para que los dispositivos conectados en una red puedan comunicarse y entenderse entre sí, hacen uso de direcciones IP, puertos, servicios y protocolos los cuáles son términos que vamos a aprender.

## Direcciones IPv4 y subredes
Este video hecho por **Gabriel Marcano** explica muy bien sobre el direccionamiento IPv4 y las subredes, de paso, apoye su contenido suscríbiendose a su canal.
<ReactPlayer controls url='https://www.youtube.com/watch?v=SHbBso63X38' width="auto" /> <br/>

👉 Del vídeo podemos concluir lo siguiente:
- Las direcciones IPv4 se expresan en connotación decimal y binaria.
- Estan compuestas de 32 bits y se separan en 4 octetos, cada uno de 8 bits.
- Existen direcciones IPv4 públicas y privadas
  - Rangos de direcciones públicas
   - Clase A: su primer octeto su rango va de 0 a 127
   - Clase B: su primer octeto su rango va de 128 a 191
   - Clase C: su primer octeto su rango va de 192 a 223
  - Rangos de direcciones privadas
    - Clase A: 10.0.0.0 a 10.255.255.255 que usa máscara de 8 bits
      - Ejemplo: 10.x.x.x/8
    - Clase B: 172.16.0.0 a 172.31.255.255 que usa máscara de 16 bits.
      - Ejemplo: 172.x.x.x/16
    - Clase C: 192.168.0.0 a 192.168.255.255 que usa máscara de 24 bits.
      - Ejemplo: 192.x.x.x/24

## Modelo OSI y TCP/IP
El modelo OSI es un modelo conceptual que define un estandar en la forma de como se comunican los dispositivos en la red.

En términos simples, es como un lenguaje universal para que los dispositivos en la red puedan comunicarse en un mismo idioma. Este modelo cenceptual se divide en 7 capas y cada una de ellas cumple con funciones estrictas y necesarias.

Revise este vídeo donde se explica que son los modelos conceptuales, que es el modelo OSI frente al modelo TCP/IP.
<ReactPlayer controls url='https://www.youtube.com/watch?v=jdKRx2BxSMs' width="auto" /> <br/>

👉 Del vídeo podemos concluir lo siguiente:
- El modelo conceptual permite que las diferentes tecnologías se comuniquen entre sí mediante un unico lenguaje o estándar
- El modelo OSI consta de 7 capas y es el modelo de referencia por todas las tecnologías:
  - Aplicación
  - Presentación
  - Sesion
  - Transporte
  - Red
  - Enlace de datos
  - Fisica
- El modelo TCP/IP consta de 4 capas y es el modelo usado para comunicaciones en redes:
  - Aplicación
  - Transporte
  - Internet
  - Acceso a la red
- Los datos pasan por una transformación al pasar por las capas del modelo OSI o TCP/IP 
  - Datos
  - Segementos
  - Paquetes
  - Tramas
  - Bits
- A los términos mencionados arriba se les conoce como PDU (Unidad de Datos de Protocolo)
- El Modelo TCP/IP consta de 4 capas pero agrupa las 7 capas del Modelo OSI
- Cada una de las capas de ambos modelos utilizan un grupo de protocolos

## Protocolos Web
Los protocolos de internet, definen un conjunto de reglas de como dos o mas dispositivos deben comunucarse entre sí, y en cada una de las capas del Modelo OSI o TCP/IP existen una serie o suite de protocolos que pueden usarse.

![protocolos tcp/ip](https://interpolados.files.wordpress.com/2017/03/16.png)

Revisa este [blog](https://openwebinars.net/blog/protocolo-de-red-que-es-tipos-y-caracteristicas/#:~:text=funciones%2C%20entre%20otros.-,Qu%C3%A9%20es%20un%20protocolo%20de%20red,-Los%20seres%20humanos) escrito por **Elena Limones** que explica cuáles son los protocolos mas usados y conocidos en cada una de las capas del modelo OSI

## Protocolo SSL/TLS
### ¿Qué es SSL?

**SSL (Secure Sockets Layer) es un protocolo de seguridad de internet basado en el cifrado** que ofrece privacidad, autenticación e integridad de los datos en las comunicaciones de internet, pero este procotolo se encuentra *ya obsoleto*. Con el tiempo evoluciono a **TLS (Transport Layer Security)** 

Por ejemplo, las paginas web en internet que empiecen con **"HTTPS"** o tengan el famoso *"candadito verde"* usan TLS.

![https](https://topofthelist.net/wp-content/uploads/2019/05/https-url.jpg)

### ¿Cómo funciona SSL/TLS?
1. Ofrece **privacidad**: SSL cifra los datos que se transmiten por la web para que cualquiera que intercepte estos mensajes, no pueda leerlos.
2. Ofrece **autenticación**: inicia un proceso conocido como establecimiento de comunicación entre dos dispositivos para asegurar que sean realmente quienes dicen ser.
3. Ofrece **integridad**: firma digitalmente los datos, con lo que puede verificar que estos no hayan sido alterados por un atacante.

### ¿Porqué es importante usar SSL/TLS?
Imagina que tienes un sitio web de ventas de artículos que incluye una pasarela de pagos, tus cliente al desear comprar algunos de tus artículos en venta, deberan ingresar su método de pago, que para este ejemplo, será el uso de sus tarjetas débito o crédito. Con esto nos referimos a que deben ingresar, en la pasarela de pagos del sitio web, la informacion de su tarjeta como los 12 dígitos, la fecha de caducidad, el cvv y el nombre del titular de la tarjeta. Al no tener implementado SSL/TLS en tu sitio web, los datos bancarios y el detalle de la compra viajaran por internet de manera legíble (texto plano), por lo que si son interceptados por un atacante, éste podrá leer y hacer uso de esos datos con facilidad.

![datos bancarios expuesto](https://i0.wp.com/unaaldia.hispasec.com/wp-content/uploads/2020/11/Prestige-Software-Leak-image2.png?resize=1024%2C491&ssl=1)

La recomendación es hacer uso de este protocolo para cifrar los datos que viajan a traves del canal de internet.

## Certificado SSL
Son los encargados de que los sitios web usen el "https".
Pero técnicamente hablando, es un archivos de datos que se almacena en el servidor web o de aplicación que aloje tu sitio. Este archivo de datos tiene dos partes: llave pública y llave privada.

La llave pública hace posible la encriptación y la autenticación. Entonces, tu navegador al obtener la llave pública de este sitio la utiliza para establecer llaves de cifrado seguras con el servidor web. Mientras tanto, el servidor web también tiene una clave privada que se mantiene en secreto; la clave privada descifra los datos cifrados con la clave pública del certificado SSL.

De esa manera, cuando visitas un sitio web, por ejemplo: `https://acloudsecurity.ninja` tu navegador hacer referencia al contenido de la llave pública para validar el contenido de este sitio web.

### ¿Qué tipo de información almacena el archivo de datos del certificado SSL?
- El nombre del dominio para el que se emitio el certificado.
- Para que organización, individuo o dispositivo se emitio el certificado.
- Que Autoridad Certificadora (CA) emitio dicho certificado.
  - Por ejemplo, Amazon
  - DigiCert
  - CloudFlare
  - Namecheap
  - GlobalSign
- La firma digital de la autoridad de certificación (CSR).
- Subdominios asociados
- Fecha de Emision y Caducidad del certificado
- Información de la llave pública

![como funciona un certificado ssl](https://acerkate.com/wp-content/uploads/2021/01/Hacer-una-sesion-segura-SSL.png)

### ¿Qué es un certificado SSL autofirmado?
Son certificados creados por cualquier usuario, como nosotros. Lo que hace que no dependamos de una CA (Certificate Authority) y se logra al emparejar una de llave pública y privada, e incluir toda la información mencionada [aquí](#qué-tipo-de-información-almacena-el-archivo-de-datos-del-certificado-ssl) y se denominan autofirmados, porque la firma digital utilizada, en lugar de ser de una CA, sería la propia clave privada del sitio web.

Pero esto no es la mejor opción, ya que no hay ninguna autoridad externa que verifique que el servidor de origen es el que dice ser, y los navegadores suelen desconfiar de los sitios web con certificados autofirmados y pueden marcarlos como sitios "no seguros," a pesar de la URL https://. En algunos casos, pueden interrumpir la conexión por completo, bloqueando la carga del sitio web.

![sitio no seguro](https://www.hostinger.es/tutoriales/wp-content/uploads/sites/7/2018/11/la-conexio%CC%81n-no-es-privada-e1541668554577-1024x368.png)

### ¿Qué tipos de certificados SSL hay?
Segun sea el tipo, los certificados pueden aplicarse a un solo sitio web o a varios:

- **Único dominio**: aplicable a un único dominio sin mas, ejemplo `workshops.aws` por lo que si en adelante crean un subdominio `test.workshop.aws` no podran hacer uso del mismo certificado SSL.

- **Comodín**: aplicable a un único dominio con la ventaja de que si se puede usar el mismo certificado SSL para todos los subdominios del dominio principal, ejemplo `test.workshop.aws`, `dev.workshop.aws`, `prod.workshop.aws`.

- **Multidominio**: aplican a varios dominios no relacionados necesariamente, por ejemplo `acloudsecurity.ninja`, `awssecuritylatam.com` entre otros.

Los certificados SSL también cuentan con diferentes niveles de validación. Un nivel de validación es como una revisión de antecedentes, y el nivel cambia dependiendo de la exhaustividad de la revisión.

- **Validación del dominio:** es el nivel de validación menos estricto y el más barato. Se valida con la comprobación de que eres el dueño del dominio que asociaras con el certificado.

- **Validación de la organización:** es un poco mas costoso pero a la vez mas confiable. la Certificate Authority se pone en contacto directamente con la persona o empresa que solicita el certificado.

- **Validación extendida:** la mas costosa y confiable de las tres. Requiere una comprobación completa de los antecedentes de una organización antes de que se emita el certificado SSL.
