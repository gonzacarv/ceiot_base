# Ejercicio CiberKillChain - Defensa

# Alumno: 
Gonzalo Carvallo

# Descripción del trabajo práctico:
El proyecto tiene como objetivo mejorar un sistema domótico existente al integrar un servidor GNU/Linux con un broker MQTT y prototipos para conexiones inalámbricas. Estos prototipos permitirán la gestión de las funciones de los módulos del sistema actual, que funcionan mediante una interfaz cableada EIA/TIA-485, a través de suscripciones al broker. 

[Link detalle del proyecto](https://drive.google.com/file/d/1biDw8UqLcxiEHpN7Hczr9RcnTaWEhQBh/view?usp=drive_link) 

*Para la finalidad del ejercicio se asumirá que el servidor además de alojar el broker MQTT también tendrá una base de datos del sistema.

# Resolución

* Objetivo: 
  - El objetivo es contar con un plan de defensa a ciberataques e incidentes.
  - Aunque la perdida de información constituiría un ataque, se considera que para la aplicación, lo critico sería perder el control del sistema (ya sea por secuestro o falla)

* Reconnaissance
  - Se debe evitar el pase de información innecesaria sobre los aspectos demóticos del hogar. La aplicación de gestión del sistema no estará disponible en internet, y las instalaciones se realizaran de manera controlada en los dispositivos necesarios. La aplicación en su interfaz no deberá exponer información innecesaria sobre el sistema o su funcionamiento.
  **T1592: Gather Victim Host Information**

* Weaponization
  - Se considera una red donde el access point para los elementos domóticos tenga un SSID oculto, y se genere un acceso WIFI para invitados separado. La comunicación del sistema en internet se hará de manera cifrada sobre un custom port.
  **T1590: Gather Victim Network Information**
    
* Delivery
  - Unicamente se expondrá el SSID para invitados. El SSID oculto solamente aceptará conexiones con filtrado de Mac Address.
  **T1590: Gather Victim Network Information**
  **T1598: Phishing for Information**
  **T1566: Phishing**
  
* Exploit
  - Se gestionará el access point para invitados de manera tal que las contraseñas de generen de manera aleatoria y tengan un vencimiento cada 30 días.
  **T1110: Brute Force**
  
* Installation
  - El router que se usará como puerta de enlace no será homologado por ninguna compañía (propiedad del usuario), y deberá tener la posibilidad de bloquear cualquier configuracion remota.
  **T1552: Unsecured Credentials**
  **T1555: Credentials from Password Stores**
  **T1598: Phishing for Information**
  
* Command & Control
  - Los usuarios del sistema demótico que intenten conectarse con adaptadores de red desconocidos, necesitarán doble factor de autenticación con su teléfono personal o el teléfono del administrador del sistema.
  **T1102: Web Service** 
  
* Actions on Objectives
  - Se deberá incluir en el servidor monitores de trafico de red y de uso de almacenamiento, que puedan detectar desvíos en relación al funcionamiento esperado. Las estadisticas y alertas serán enviadas al administrador del sistema de forma semanal. 

