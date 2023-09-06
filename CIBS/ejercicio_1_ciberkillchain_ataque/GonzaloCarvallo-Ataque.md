# Ejercicio CiberKillChain - Ataque

# Alumno: 
Gonzalo Carvallo

# Descripción del trabajo práctico:
El proyecto tiene como objetivo mejorar un sistema domótico existente al integrar un servidor GNU/Linux con un broker MQTT y prototipos para conexiones inalámbricas. Estos prototipos permitirán la gestión de las funciones de los módulos del sistema actual, que funcionan mediante una interfaz cableada EIA/TIA-485, a través de suscripciones al broker. 

[Link detalle del proyecto](https://drive.google.com/file/d/1biDw8UqLcxiEHpN7Hczr9RcnTaWEhQBh/view?usp=drive_link) 

# Resolución

* Objetivo: 
  - No identifico objetivos redituables mediante la obtención de información, ni ransomware. El objetivo del ataque será el almacenaje y procesamiento de información ilegal.

* Reconnaissance
  - Identifico/recibo información sobre un hogar que gestiona periféricos demóticos mediante una aplicación propia. Se obtiene la ubicación del hogar.
  **T1592: Gather Victim Host Information**

* Weaponization
  - Planifico visita de campo dentro del alcance tentativo de las redes Wi-Fi del hogar. El objetivo será realizar sniffing de paquetes, reconocimiento de red/equipos.
  **T1590: Gather Victim Network Information**
    
* Delivery
  - Se asiste con un vehículo hasta zona de alcance Wi-Fi de la red del hogar en la vía publica, el equipo dentro del automóvil cuenta con 2 computadoras con placas de red inalámbricas y carga eléctrica permanente para los equipos.
  **T1590: Gather Victim Network Information**
  **T1598: Phishing for Information**
  **T1566: Phishing**
  
* Exploit
  - Se logra crackear la conexión WPA2 obteniendo el acceso a la red local // Se obtiene la contraseña por parte de la víctima.
  **T1110: Brute Force**
  
* Installation
  - Desde la red local logro acceder a la configuración de administrador del router (puerta de enlace a internet). Desde la configuración del router,  cambio la IP fija del servidor, y en la IP del servidor se coloca un falso portal para la pesca de credenciales.
  **T1552: Unsecured Credentials**
  **T1555: Credentials from Password Stores**
  **T1598: Phishing for Information**
  
* Command & Control
  - Luego del logueo de un perfil de administrador, se obtienen las credenciales logrando el acceso al servidor mediante los servicios que ofrece.
  **T1102: Web Service** 
  
* Actions on Objectives
  - Con los permisos de administrador, se identifican bandas horarias de pozo uso del servidor, y durante las mismas se realizan las copias de información ilegal al mismo, las aplicaciones para el procesamiento y gestión de la misma. Se configuran los accesos necesarios para disponer de la información.

