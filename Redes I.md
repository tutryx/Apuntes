# Redes I
## Clasificacion de redes
* **PAN** (Redes de Área Personal): Conexiones como Bluetooth que abarcan el área cercana a una persona.
* **LAN** (Redes de Área Local): Conectan dispositivos dentro de un espacio reducido, como oficinas o edificios, con gestión y propiedad local.
* **MAN** (Redes de Área Metropolitana): Cubre áreas urbanas con tecnologías como televisión por cable.
* **WAN** (Redes de Área Amplia): Conectan grandes áreas geográficas usando ISP. Pueden usar conmutación de circuitos o paquetes.
### Conmutación de circuitos
Se establece una ruta fija a través de nodos.
### Conmutación de paquetes
Los datos se envían en pequeñas unidades que son almacenadas y redirigidas dinámicamente en cada nodo.
## Tipos de redes
* **Redes Broadcast**: El mensaje es enviado desde una fuente y recibido por múltiples destinatarios. Un ejemplo común es una transmisión de televisión o radio.
* **Redes Unicast**: El mensaje es enviado desde una fuente específica a un destinatario particular. Es la forma más común de transmisión en redes como Internet.
* **Redes Multicast**: El mensaje es enviado a un grupo selecto de destinatarios. Se utiliza en aplicaciones como videoconferencias.
## Tipos de Servicio
* **Orientados a la Conexión**: Establece una conexión dedicada entre dos puntos antes de que se puedan transmitir datos. Se realiza una negociación de parámetros antes de enviar los datos. Una vez terminada la comunicación, la conexión se cierra.
* **No Orientados a la Conexión**: Los datos se envían en forma de mensajes independientes, sin necesidad de establecer una conexión previa. No hay negociación previa de parámetros, y no se garantiza que los datos lleguen en un orden específico.
## Topologias
![image](https://imgur.com/a/82ZzWWB)
### Quality Of Service
Es el rendimiento visto por los usuarios de la red.
### Traffic Engineering
Es la planificacion, diseño y desarrollo de las redes de acuerdo a las demandas para maximizar el rendimiento.
# Modelos
![image](https://imgur.com/a/7hvIuQz)
# Capa de Enlace
Se encarga de garantizar una comunicación eficiente y confiable entre dos máquinas.
### Sus principales funciones incluyen:
1. Proporcionar una interfaz definida con la capa de red
2. Reconocimiento de tramas
3. Manejo de errores de transmisión
4. Control de flujo

Se encapsulan los datos de la capa de red en **tramas**:
* **Header**: Información de control.
* **Payload**: Datos reales transmitidos.
* **Trailer**: Datos para verificar la integridad de la trama, como el CRC.
### Sincronización
* **Conteo de caracteres**: Se utiliza un campo de longitud en el encabezado para indicar el tamaño de la trama.
* **Flags de inicio y fin**: Se agregan caracteres especiales (01111110) al inicio y fin.
### Control de Errores
Utiliza mecanismos como CRC o Checksum para detectar errores y, si es necesario, solicitar la retransmisión de las tramas defectuosas.
### Control de Flujo
* **Stop & Wait**: El emisor envía una trama y espera su confirmación antes de enviar la siguiente.
* **Ventana Deslizante**: Permite que el emisor envíe múltiples tramas antes de recibir confirmaciones.
* ## Control de acceso al medio
Regula el acceso al canal compartido en redes de difusión. Métodos de asignación de canal:
### Asignación estática
FDM (Multiplexación por División de Frecuencia) o TDM (Multiplexación por División de Tiempo).
El canal se divide en partes asignadas a cada estación.
### Asignación dinámica
Se utiliza un solo canal compartido donde pueden ocurrir colisiones, y se aplican protocolos para evitar o gestionar estas colisiones:
* **ALOHA Puro**: Las estaciones transmiten cuando tienen datos y, en caso de colisión, esperan un tiempo aleatorio antes de retransmitir.
* **ALOHA Ranurado**: Similar a ALOHA puro, pero las transmisiones solo ocurren en intervalos de tiempo específicos (slots).
* **CSMA (Carrier Sense Multiple Access)**: Las estaciones escuchan el canal antes de transmitir para verificar si está libre.
* **CSMA/CD (Carrier Sense Multiple Access with Collision Detection)**: Extiende el CSMA al detectar colisiones mientras transmite y abortar la transmisión en caso de que ocurra una colisión. Luego, las estaciones esperan un tiempo aleatorio antes de intentarlo de nuevo.
# Ethernet
Estándar ampliamente utilizado para redes locales (LAN) que permite la interconexión de dispositivos en una red, utiliza **CSMA/CD** a excepcion de que sea **Full Duplex**.
## Trama
* **MAC Destino** 6 bytes
* **MAC Origen** 6 bytes
* **Tipo** 2 bytes
      1. __<0x0600__ IEEE 802.3 Size
     2. __0x0800__ IPv4
     3. __0x0806__ ARP
* **Datos** 46-1500 bytes
* **CRC** 4 bytes
## Estandares
* **100Base-TX** UTP | 100m | 100Mbps
* **100Base-FX** Fibra Optica | 2000m | 100Mbps
* **1000Base-SX** Fibra Optica  | 550m | Fibra multimodo
* **1000Base-LX** Fibra Optica | 5000m | Fibra monomodo
* **1000Base-T** UTP | 100m | UTP cat 6
* **10GBase-SR** Fibra Optica | 300m | Fibra multimodo
* **10GBase-LR** Fibra Optica | 10Km | Fibra monomodo
* **10GBase-ER** Fibra Optica | 50Km | Fibra monomodo
* **10GBase-T** UTP | 100m | UTP Cat 6a
# Redes inalambricas
### RFID
Identificacion por radiofrecuencia. Usa ondas de radio para leer, transmitir y capturar información almacenada en
una etiqueta que está adjunta a un objeto.
### Bluetooth
Facilita las comunicaciones entre dispositivos móviles. Opera en la banda ISM de 2,4 GHz y usa FHSS (Frecuencia de Salto).
## WiFi
Facilita la conexión inalámbrica entre dispositivos.
### Frecuencias
* **2.4 GHz**
 * Mayor alcance pero menor velocidad.
 * Propenso a interferencias.
 * Solo 3 canales no se superponen: 1, 6 y 11.
* **5 GHz**
 * Menor alcance y mayor velocidad.
 * Menos propenso a interferencia.
 * Más canales disponibles.
### Estandares
* 802.11 | 1-2 Mbps | 2,4 GHz.
* 802.11b | 11 Mbps | 2,4 GHz.
* 802.11g | 54 Mbps | 2,4 GHz.
* 802.11ac (WiFi 5) 1,3 Gbps | 2,4 y 5 GHz.
* 802.11ax (WiFi 6): Más eficiente | Mejor manejando muchos usuarios
### SSID
Es el identificador de la red inalámbrica (nombre de la red). Se puede ocultar.
### Beacon
Es un tipo de paquete que los puntos de acceso WiFi envían periódicamente para anunciar la existencia de la red y proporcionar información de configuración.
### Proceso de asociación
1. **Escaneo**
2. **Autenticación**
3. **Asociación**
### Metodos de autenticacion
* **WEP (Wired Equivalent Privacy)**
  * Uno de los primeros, se considera inseguro y obsoleto.
* **WPA (Wi-Fi Protected Access)**
  * Utiliza una clave de cifrado temporal que se actualiza periódicamente.
* **WPA2**
  * Incluye un algoritmo de cifrado más seguro: AES (Advanced Encryption Standard).
  * **WPA2-Personal:** Utiliza una clave precompartida (PSK - Pre-Shared Key).
  * **WPA2-Enterprise:** Autenticación basada en servidor generalmente RADIUS.
* **WPA3**
  * Protección mejorada para redes abiertas (sin contraseña), encriptando el tráfico aún sin autenticación.
