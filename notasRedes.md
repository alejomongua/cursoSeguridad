# 2020-11-20

## Contenido:

Fundamentos de networking

Direccionamiento IPv4, IPv6

Aseguramiento de red en capa 2 y capa 3

Ataques de red comunes

Software de aprendizaje de networking y emulación de redes

## Fundamentos de networking

### Que es una red

Es la interconexión de dos o más computadoras para compartir información y/o establecer comunicación entre sí

Tipos de dispositivos:

* Equipos finales o terminales de red (Host)

* Dispositivos activos de la red (Router, Firewall, bridge, etc)

### Tamaño de las redes de datos

PAN: Red de área personal
LAN: Red de área local
CAN: Red de area campus
MAN: Red de area metropolitana
WAN: Red de area amplia

### Conjuntos de protocolos

![Conjuntos de protocolos](images/conjuntos-de-protocolos.png)

Hay muchos conjuntos de protocolos:

![Ejemplo de TCP/IP](images/ejemplo-tcp-ip.png)

TCP/IP (El más utilizado) -> Operan en la capa de aplicación, transporte e internet. Los protocolos LAN de acceso a la red más comunes son Ethernet y WAN

Protocolos OSI

Apple Talk (propietario)

Novell Netware (propietario)

### Suite de protocolos TCP/IP

![Suites de protocolos TCP/IP](images/suit-de-protocolos-tcp-ip.png)

Protocolos abiertos, incluye muchos protocolos

#### Capa de aplicación

DNS: Nombres de dominio

DHCP, SLAAC: Host config

SMTP, POP3, IMAP: Email

FTP, SFTP, TFTP: Transferencia de archivos

HTTP, HTTPS, REST: Web

#### Capa de transporte

TCP: Orientado a conexión, se confirma la recepción de cada paquete, es más robusto que UDP

UDP: Connectionless, puede tener pérdidas, muy util en comunicación en tiempo real, es más ligero que TCP

#### Capa de internet

IPv4, IPv6, NAT: Internet protocol

IMCP: Mensajería

OSPF, EIGRP, BGP: Enrutamiento

#### Capa de acceso a la red

ARP: Resolución de direcciones

Ethernet, WLAN: Data link

### Proceso de comunicación TCP/IP

![Proceso de comunicación TCP/IP](images/proceso-de-comunicacion-tcp-ip.png)

Un servidor encapsula y envía una página web a un cliente

Un cliente desecapsula la página web para el navegadorpro

### Estándares abiertos

![Estandares abiertos](images/estandares-abiertos.png)

Los estándares abiertos fomentan:

* Interoperabilidad

* Competencia

* Innovacion

#### Organizaciones

* Internet corporation for assigned names and numbers ICANN

* Internet assigned numbers authority (IANA)

### Estándares electrónicos y de comunicaciónes

IEEE

EIA

TIA

UIT-T

### Beneficios de utilizar modelo de capas

![](images/modelos-de-capas.png)

Los conceptos complejos de como funciona la red pueden ser difíciles de explicar y comprender, por este motivo se utiliza un modelo en capas

Dos modelos en capas describen las operaciones de red:

* Modelo de referencia de interconexión de sistema abierto (OSI)

* Modelo de referencia TCP/IP

### Beneficios de utilizar un modelo de capas

Ayudar en el diseño de protocolos porque los protocolos que operan en una capa específica han definido la información sobre la que actuan

### Modelo OSI

7 - Aplicación: Utilizados para las comunicaciones de proceso a proceso, permite la interacción usuario máquina en un lenguaje común

6 - Presentación: Proporciona una representación común de los datos requeridos entre los servicios de capa de aplicación de manera que permite dar el formato a los datos para que puedan ser abiertos con la aplicación correcta.

5 - Sesión: Se proporcionan servicios a la capa de presentación y para administrar el intercambio de datos

4 - Transporte: Define los servicios para segmentar, transferir y volver a ensamblar los datos para las comunicaciones individuales, permite que exista la comuicación de extremo a extremo, también garantiza que los datos sean entregados en el orden correcto sin cambios y sin modificaciones cuando es orientada a conexión. Cuando la comunicación no es orientada a comunicación permite que la comunicación se envíe del origen al destino de forma rápida.

3 - Red: Proporciona servicios para intercambiar datos individuales a través de la red

2 - Enlace de datos: Describe los métodos para intercambiar marcos de datos a través de un medio común, de esta capa para arriba todo es software, de aquí para abajo todo es hardware. En esta capa reside el direccionamiento físico BIA, se divide en 2 subcapas: MAC y LLC

1 - Física: Describe los medios para activar, mantener y desactivar las conexiones físicas, aquí está el hardware de red, medios, conectores y diferentes estándares, la PDU son los bits.

### Modelo TCP/IP

Aplicación

Transporte

Internet

Acceso a red

### OSI vs TCP/IP

![Comparación entre TCP/IP u OSI](images/osi-vs-tcp-ip.png)

## Dispositivos de red

### Funcionamiento del HUB o Concentrador

Son dispositivos de capa 1

Su mecanismo de transmisión es half duplex

Utiliza 2 hilos para transmitir y los mismos 2 para recibir

Se comporta como un cable, es decir, no modifica ni altera la información que pasa a través de él

Es un dispositivo "tonto" por no tener procesamiento de la información

Todo el HUB es un completo dominio de colisión

Recibe la información por uno de sus puertos y siempre trasmite por todos los demás

Divide el ancho de banda entre los dispositivos conectados

### Switch o conmutador

Tienen una tabla de MAC, cachea la MAC cuando un host envía información, asocia la MAC al puerto al que está conectados

Solo la primera vez que recibe una trama por un puerto la reenvía por todos los demás puertos. A partir de este momento, si necesitace reenviar información al mismo destino solamente la enviará al puerto que tenga la MAC correspondiente al destino

Cada host conectado a un switch conserva el 100 % del ancho de banda y garantiza un medio libre de colisiones

### Routers

Trabajan en la capa 3

## Software de aprendizaje de networking

![Cisco packet tracer](images/cisco-packet-tracer.png)

Cisco packet tracer

Curso gratuito de packet tracer https://www.netacad.com/es/courses/packet-tracer/introduction-packet-tracer

NOTA: Dispositivos de capas diferentes se conectan con cable directo, si son de la misma capa se usa cable cruzado

Cantidad de dominios de broadcast = cantidad de redes LAN

Cantidad de dominios de colisión = Puertos del Switch

TTL -> Cantidad de saltos entre redes

### IOS

Sistema operativo de dispositivos de comunicación Cisco

#### CLI

##### Modo de usuario

Solo lectura

prompt >

`enable` para pasar al modo privilegiado

##### Modo privilegiado

Permite configurar el dispositivo

prompt #

`disable` para cambiar al modo usuario

`configure terminal` para cambiarse al modo config

`write` para escribir la configuración

##### Modo global config propt (config)#

modo sub config (cofig-if)#

`end` para salir al modo privilegiado

# 2020-11-23

## Software GNS3

GNS3 es un simulador gráfico de red lanzado en 2008, que te permite diseñar topologías de red complejas y poner en marcha simulaciones sobre ellos permitiendo la combinación de dispositivos tanto reales como virtuales.

### Instalación:

    pip3 install gns3-gui gns3-server pyqt5

se ejecuta con:

    gns3

# 2020-11-25

## Protocolo IPv4

Tiene longitud de 32 bits, se divide en cuatro grupos de 8 bits cada uno llamados octetos, se representan en sistema decimal

El formato es X.X.X.X donde cada X es un número entero entre 0 y 255

Existen aproximadamente 4000 millones de IPs

Tiene jerarquía, esto indica que está dividido en 2 partes: red y host

La parte de red es la que cubre la máscara

### Clases de IPv4 (obsoleto)

Fue reemplazado en 1993 por CIDR porque se desperdiciaban muchas direcciones

#### Clase A

Rango: 0.0.0.0 a 127.255.255.255, máscara de 8

#### Clase B

Rango 128.0.0.0 a 191.255.255.255 máscara de 16

#### Clase C

Rango 192.0.0.0 a 223.255.255.255 máscara de 24

#### Clase D

Rango 224.0.0.0 a 239.255.255.255

#### Clase E

Rango 240.0.0.0 a 255.255.255.255

### Rangos especiales de IPv4

#### Rangos privados RFC 1918

Clase A: 10.0.0.0-10.255.255.255
Clase B: 172.16.0.0-172.31.255.255
Clase C: 192.168.0.0-192.168.255.255

#### Rango no específico

0.0.0.0 - 0.255.255.255 solo utilizadas como direcciones de origen

#### Red privada de NAT de proveedor de servicios

100.64.0.0 - 100.127.255.255, se utilizan para la comunicaicón de un proveedor de servicio y los clientes cuando se realiza nuevamente un NAT por parte del proveedor

#### Rango de bucle invertido

127.0.0.0 - 127.255.255.255 -> Se asigna 127.0.0.1 a localhost

#### Direcciones de documentación o Test-NET

192.0.2.0 - 192.0.2.255

### Máscara de subred

Separa la porción de host de la porción de red: La parte de red está enmascarada

### CIDR

Classless interdomain routing, reemplazó las clases de IPv4, es una técnica que permite dividir las direcciones IP de una manera mucho más flexible

El mascarado no se limita a los límites de los octetos

### Análisis de tipos de IP dentro de una red

Direcciones de identificación de red, host y difusión

#### Dirección de identificación de red

Es la primera dirección de la red (no asignable), que se caracteriza porque todos los bits de la porción de host son ceros

#### Primera dirección de host

Es la primera dirección válida o asignable a un host en la red que se caracteriza porque todos los bits de la porción de host son 0 excepto el último

#### Última dirección de host

Es la última dirección válida o asignable a un host en la red que se caracteriza porque todos los bits de la porción de host son 1 excepto el último que es 0

#### Dirección de multidifusión (broadcast)

Es la última dirección de la red (no asignable), que se caracteriza porque todos los bits de la porción de host son 1

#### Rango asignable:

Todas las direcciones entre la primera dirección de host y última dirección de host (inclusive)

#### Dirección de la puerta de enlace o gateway

Es cualquier dirección válida de la red que se configura a la interface de un router para permitir la comuicación hacia redes externas.

### Problems de redes grandes

Exceso de generación de mensajes de difusión que puede impactar negativamente en el rendimiento de la red

* Operaciones de red bastante lentas

* Sobrecarga en el proceso de los host, debido al exceso de broadcast

Todos los host en una misma red plantea un desafio de administración y seguridad

* Si algún equipo de la red es afectado por un virus o malware, este puede propagarse de manera directa a los demás equipos de la red local

* Se torna más complejo realizar la aplicaicón de políticas de seguridad para una red no segmentada

La solución es reducir el tamaño de la red dividiendola en redes más pequeñas

Es posible realizar la división en subredes teniendo en cuenta aspectos físicos como:

* Ubicación: ciudad, piso, edificio, etc

* Area o departamento de la empresa: Contabilidad, administración, ventas, producción

* Tipos de dispostivo: Impresoras, servidores, cámaras, portátiles, etc

### Ejemplo de subdivisión de red

Dividir la red 172.16.0.0/16 en cinco subredes de tamaño /19

| Subred | Máscara       | CIDR | IP de red    | Rango asignable               | Broadcast      | Tamaño |
| ------ | ------------- | ---- | ------------ | ----------------------------- | -------------- | ------ |
| 1      | 255.255.224.0 | /19  | 172.16.0.0   | 172.16.0.1 - 172.16.31.254    | 172.16.31.255  | 8190   |
| 2      | 255.255.224.0 | /19  | 172.16.32.0  | 172.16.32.1 - 172.16.63.254   | 172.16.63.255  | 8190   |
| 3      | 255.255.224.0 | /19  | 172.16.64.0  | 172.16.64.1 - 172.16.96.254   | 172.16.96.255  | 8190   |
| 4      | 255.255.224.0 | /19  | 172.16.96.0  | 172.16.96.1 - 172.16.127.254  | 172.16.127.255 | 8190   |
| 5      | 255.255.224.0 | /19  | 172.16.128.0 | 172.16.128.1 - 172.16.160.254 | 172.16.160.255 | 8190   |

Dividir la red 100.64.0.0/10 en las siguietes subredes

a. 850 host
b. 197 host
c. 432 host
d. 62 host
e. 1398 host

| Subred | Máscara         | CIDR | IP de red    | Rango asignable               | Broadcast      | Tamaño |
| ------ | --------------- | ---- | ------------ | ----------------------------- | -------------- | ------ |
| e      | 255.255.248.0   | /21  | 100.64.0.0   | 100.64.0.1 - 100.64.7.254     | 100.64.7.255   | 2046   |
| a      | 255.255.252.0   | /22  | 100.64.8.0   | 100.64.8.1 - 100.64.11.254    | 100.64.11.255  | 1022   |
| c      | 255.255.254.0   | /23  | 100.64.12.0  | 100.64.12.1 - 100.64.13.254   | 100.64.13.255  | 510    |
| b      | 255.255.255.0   | /24  | 100.64.14.0  | 100.64.14.1 - 100.64.14.254   | 100.64.14.255  | 253    |
| d      | 255.255.255.192 | /26  | 100.64.15.0  | 100.64.15.1 - 100.64.15.62    | 100.64.15.63   | 62     |

Una universidad requiere diseñar la división de su red de acuerdo a sus areas, a partir de la IP 10.20.0.0/16, realice el direccionamiento de las siguietnes subredes

Docentes: 90 hosts
Estudiantes: 2250 hosts
TI 30 hosts
Administrativo 36 hosts
Recursos humanos 14 hosts

| Subred      | Máscara         | CIDR | IP de red    | Rango asignable             | Broadcast      | Tamaño |
| ----------- | --------------- | ---- | ------------ | --------------------------- | -------------- | ------ |
| Estudiantes | 255.255.240.0   | /20  | 10.20.0.0    | 10.20.0.1 - 10.20.15.254    | 10.20.15.255   | 4094   |
| Docentes    | 255.255.255.128 | /25  | 10.20.16.0   | 10.20.16.1 - 10.20.16.127   | 10.20.16.255   | 126    |
| Admin       | 255.255.255.192 | /26  | 10.20.16.128 | 10.20.16.129 - 10.20.16.190 | 10.20.16.191   | 62     |
| TI          | 255.255.255.224 | /27  | 10.20.16.192 | 10.20.16.193 - 10.20.16.222 | 10.20.16.223   | 30     |
| RRHH        | 255.255.255.240 | /28  | 10.20.16.224 | 10.20.16.225 - 10.20.16.238 | 10.20.16.239   | 14     |

## IPv6

Contiene direcciones de 128 bits

Se representa en hexadecimal, se separa en 8 grupos de 16 bits cada uno
