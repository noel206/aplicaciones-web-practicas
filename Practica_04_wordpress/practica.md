# Práctica: Practica_04_wordpress

**Nombre:** Noel Hidalgo Ortí

**Curso:** Sistemas Microinformáticos y Redes (SMR) - Módulo: Aplicaciones Web

**Fecha:** 28 de octubre de 2026

**Apartado 1. Conexión por SSH y comprobación del servidor**

**1.3. Comprueba que todo lo anterior sigue funcionando:**
<img width="534" height="156" alt="Captura de 2026-10-23 09-32-29" src="https://github.com/user-attachments/assets/b25ffbd6-5c43-4379-be23-2468f16c6e7f" />


**¿Qué dos "puertas" (programas y puertos) usas para trabajar con el servidor en esta práctica y para qué sirve cada una?**
SSH (puerto 22) con la terminal para administrar el servidor, y HTTP (puerto 80) con el navegador para ver y usar WordPress.
**Apartado 2. Dejar Apache con un único sitio**


**2.1. Cambia los sitios activos:**

<img width="471" height="188" alt="Captura de 2026-10-23 09-40-52" src="https://github.com/user-attachments/assets/de55beb7-f26c-46be-b20a-4c9ab74fc8b3" />

**2.2. Comprueba que solo hay un sitio activo y qué carpeta usa:**
<img width="621" height="123" alt="Captura de 2026-10-23 09-43-42" src="https://github.com/user-attachments/assets/412dcb52-9849-49f6-8f4c-411939aaf34a" />

**2.3. Comprueba que tu navegador llega al servidor.**
<img width="954" height="514" alt="Captura de 2026-10-28 09-42-18" src="https://github.com/user-attachments/assets/3a6c4c92-91be-471a-8e4b-bb370671b91d" />

**Qué diferencia hay entre desactivar un sitio con a2dissite y borrar sus ficheros? ¿Por qué ahora ves la página por defecto de Apache y antes veías sitio1?**
a2dissite solo desactiva el sitio quitando su acceso, pero guarda intactos los archivos. Ves la página por defecto porque desactivamos sitio1 y volvimos a activar 000-default.conf.

**Apartado 3. Crear la base de datos de WordPress**
<img width="685" height="609" alt="Captura de 2026-10-28 09-48-26" src="https://github.com/user-attachments/assets/bb293c82-4a87-48c3-9f0c-478319faed8f" />

**¿Por qué crees que WordPress usa su propio usuario wp_user con permiso solo sobre su base y no el usuario root de MariaDB?**
Por seguridad. Si un atacante entra a WordPress, solo tendrá acceso a su base de datos (wordpress) y no comprometerá todo el servidor (como pasaría usando root).


**Apartado 4. Descargar e instalar los ficheros de WordPress**

**4.1. Descarga y descomprime WordPress**
<img width="944" height="514" alt="Captura de 2026-10-28 13-01-27" src="https://github.com/user-attachments/assets/ca2054d1-aab8-4733-9700-b7929fc55f63" />

**4.2. Colócalo en la carpeta de tu sitio.**
<img width="943" height="260" alt="imagen" src="https://github.com/user-attachments/assets/dc2c446b-5045-4434-ab36-4146e82ef90a" />

rm index.html: Borra la página por defecto de Apache.   
cp -a: Copia los archivos de WordPress a la carpeta web.   
rm -r: Elimina los archivos temporales descargados.   
ls: Comprueba que los archivos de WordPress están en su sitio. 
**Explica qué hace cada uno de los comandos que acabas de ejecutar.**

**4.3. Dale los permisos correctos.**
<img width="547" height="106" alt="imagen" src="https://github.com/user-attachments/assets/5e4c6a3f-0cb1-4fbd-9e1c-b3eedee94aea" />

**Explica qué hace cada una de las órdenes que has ejecutado. ¿Por qué hay que cambiar el propietario de la carpeta de WordPress a www-data? ¿Qué podría fallar si siguiera siendo tu usuario?**
chown: Hace que Apache (www-data) sea el dueño de la carpeta.   
find + chmod: Asigna los permisos correctos a carpetas (755) y ficheros (644).  
Se cambia a www-data para que WordPress pueda escribir (subir fotos, instalar plugins). Si siguiera con tu usuario, WordPress daría error por falta de permisos.

**Apartado 5. Terminar la instalación desde el navegador (la parte gráfica)**

<img width="578" height="451" alt="imagen" src="https://github.com/user-attachments/assets/d18bacb4-e26d-4287-ba0f-35a85c852da1" />

<img width="592" height="431" alt="imagen" src="https://github.com/user-attachments/assets/db77cb20-f42f-419b-a125-5d0676678915" />

**¿Qué partes de la instalación has hecho en la terminal y cuáles en el navegador? ¿Por qué el servidor no necesita tener interfaz gráfica?**
En terminal: preparar Apache, base de datos y descargar ficheros. En navegador: configuración gráfica de base de datos y administrador. El servidor no necesita entorno gráfico porque solo envía código; es el navegador de tu PC el que dibuja la interfaz.

**Apartado 6. Comprobamos que WordPress funciona**

**6.1. La web pública.**
<img width="767" height="408" alt="imagen" src="https://github.com/user-attachments/assets/50fba2a2-3166-40d3-b73d-8a344a74e987" />

**6.2. El panel de administración.**
<img width="955" height="446" alt="imagen" src="https://github.com/user-attachments/assets/7ae89f2b-e435-4317-8dca-10589a0685b1" />

**6.3. Publica una entrada de prueba.**
<img width="962" height="332" alt="imagen" src="https://github.com/user-attachments/assets/88587cc1-f1fe-4e6c-904c-8bf73800a52d" />

**6.4. ¿Dónde ha guardado WordPress tu entrada?**
<img width="461" height="330" alt="imagen" src="https://github.com/user-attachments/assets/e66bcc30-a23c-4d00-825b-a34a9718591e" />

**¿Dónde guarda WordPress las entradas que escribes: en ficheros del servidor o en la base de datos? ¿Cómo lo has comprobado?**
Las guarda en la base de datos (en la tabla wp_posts). Se comprueba ejecutando el comando SHOW TABLES; dentro de MariaDB.   

**Apartado 7. Para que no se rompa si cambia la IP (recomendado)**
<img width="504" height="50" alt="imagen" src="https://github.com/user-attachments/assets/49aef070-c0f9-419b-8282-3b6478a3db0b" />

<img width="451" height="38" alt="imagen" src="https://github.com/user-attachments/assets/2c3b3947-2642-4076-9d77-5c350e7370d9" />

**8.1. Direcciones "bonitas" (enlaces permanentes).**
<img width="551" height="227" alt="imagen" src="https://github.com/user-attachments/assets/d8d8d497-02fc-4045-81e4-23f4ce57f957" />

<img width="634" height="60" alt="imagen" src="https://github.com/user-attachments/assets/6f2b561a-8a65-4943-ba74-0e84e67bd747" />

**8.2. Poder subir ficheros grandes.**
<img width="952" height="113" alt="imagen" src="https://github.com/user-attachments/assets/e873c2ec-8e4c-4e66-8386-284b40b8b91c" />

**¿Por qué las direcciones "bonitas" dan error 404 si Apache no tiene permitido leer el fichero .htaccess?**
Porque la estructura de las URL bonitas se define en el archivo .htaccess. Si Apache no tiene permiso para leerlo (AllowOverride All), no sabrá qué hacer con esa URL y devolverá un error 404.

**Apartado 9. ¿Qué pasa si MariaDB se para?**

<img width="944" height="193" alt="imagen" src="https://github.com/user-attachments/assets/79865d75-c78c-4104-a2bd-582392baf0db" />

<img width="951" height="444" alt="imagen" src="https://github.com/user-attachments/assets/0bbec8ab-218f-469a-a888-feb68a1b710c" />

**Cuando WordPress muestra "Error al establecer una conexión con la base de datos", ¿qué dos cosas comprobarías y en qué orden?**
1º Comprobar si MariaDB está arrancado (systemctl is-active mariadb).
2º Comprobar que el usuario y la contraseña sigan siendo correctos.


**Apartado 10. Comprobación final**

<img width="567" height="478" alt="imagen" src="https://github.com/user-attachments/assets/dad1d6b6-6873-4371-bd02-06c2c0f5d2af" />


| Pieza | Programa | Estado |
| :--- | :--- | :--- |
| Linux | Ubuntu 24.04 | Instalado |
| Apache | Apache2, con un único sitio | Funcionando |
| MariaDB | MariaDB 10.11 | Funcionando, con la base wordpress |
| PHP | PHP 8.3 | Funcionando |
| WordPress | Instalado en /var/www/html | Funcionando y accesible desde el navegador |

| Dato | Valor |
| :--- | :--- |
| Dirección de la web | http://192.168.56.27 |
| Panel de administración | http://192.168.56.27/wp-admin |
| Usuario administrador | N0eL |
| Contraseña | La que creaste |
