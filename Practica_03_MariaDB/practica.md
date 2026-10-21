# Práctica: Instalación, configuración y securización de Apache en Ubuntu 24.04

**Nombre:** Noel Hidalgo Ortí

**Curso:** Sistemas Microinformáticos y Redes (SMR) - Módulo: Aplicaciones Web

**Fecha:** 21 de octubre de 2026

**Apartado 1. Preparación del sistema**

<img width="343" height="52" alt="imagen" src="https://github.com/user-attachments/assets/fc487d27-b6e5-49b2-83ac-5a6567f669c0" />

**Apartado 2. Instalación de MariaDB**
<img width="787" height="58" alt="imagen" src="https://github.com/user-attachments/assets/5404c31b-7754-4def-8f67-9b09e28c65d2" />

**Apartado 3. Comprobación del funcionamiento**

**3.1. Estado del servicio**
<img width="751" height="257" alt="imagen" src="https://github.com/user-attachments/assets/47ef91a8-1b6d-43f8-b8d9-cd8d313e0af3" />

**3.2. Entrar en la base de datos**
<img width="642" height="220" alt="imagen" src="https://github.com/user-attachments/assets/4f1966a3-a0bf-44af-8a0b-cb3b0736d60b" />

**Apartado 4. Comandos principales**

| Comando | Función |
| :--- | :--- |
| `sudo systemctl start mariadb` | Arranca el servicio |
| `sudo systemctl stop mariadb` | Detiene el servicio |
| `sudo systemctl restart mariadb` | Reinicia el servicio |
| `sudo systemctl status mariadb` | Muestra su estado |
| `sudo systemctl enable mariadb` | Lo arranca automáticamente al encender el equipo |

**Apartado 5. ¿Qué pasa si MariaDB está parado?**

<img width="758" height="117" alt="imagen" src="https://github.com/user-attachments/assets/22ea10b5-fbe6-4d2b-8307-27ab2cd35085" />

**Si WordPress no pudiera conectar con la base de datos, ¿qué dos comandos de este apartado usarías
para saber si el problema es que MariaDB está parado?**
systemctl is-active mariadb
sudo mariadb

**Apartado 6. Instalación de PHP**

<img width="535" height="105" alt="imagen" src="https://github.com/user-attachments/assets/dd255d7c-2b76-41b9-909d-10999896b6fb" />

<img width="947" height="604" alt="imagen" src="https://github.com/user-attachments/assets/baf5d931-63d9-4a79-984f-d65984e73f18" />

**¿Por qué es peligroso dejar info.php en un servidor real?**
Porque muestra públicamente información confidencial del servidor (versión exacta de PHP, módulos activos, rutas internas del sistema y variables de entorno). Un atacante puede usar esos datos para encontrar vulnerabilidades específicas y hackear la web.  

**¿Para qué sirve el paquete php-mysql?**
Es el "puente" o conector que permite que el lenguaje PHP pueda comunicarse con una base de datos MySQL o MariaDB para guardar, consultar o borrar información.

**Apartado 7. Comprobación final**

<img width="579" height="153" alt="imagen" src="https://github.com/user-attachments/assets/040e486d-2109-4ebd-9cf9-08c7b45665ad" />
