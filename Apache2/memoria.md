# apache
1. version de ubuntu:
<img width="285" height="101" alt="imagen" src="https://github.com/user-attachments/assets/53d12344-7a4d-460f-b0c7-52362c2630e5" />

2. Aqui he instalado apache2 y he comprobabado la version que tiene:
<img width="349" height="14" alt="imagen" src="https://github.com/user-attachments/assets/fbc1d1c0-2b7a-460d-b0f3-8f969f5f7088" />
<img width="309" height="50" alt="imagen" src="https://github.com/user-attachments/assets/d00da449-5e37-433b-a9b7-c4d7861fd919" />

**PREGUNTA 1**:**¿Qué paquetes adicionales se han instalado como dependencias? (pista: revisa la salida de apt)**:

apache2 apache2-bin apache2-data apache2-utils libapr1t64 libaprutil1-dbd-sqlite3 libaprutil1-ldap libaprutil1t64
liblua5.4-0 ssl-cert

<img width="923" height="104" alt="imagen" src="https://github.com/user-attachments/assets/769335f1-d461-4389-ae5c-07b93d382a51" />

3.1. Estado del servicio instalado

<img width="955" height="286" alt="Captura de 2026-10-07 09-46-53" src="https://github.com/user-attachments/assets/fafb8930-c2f9-4ed9-8885-5d2918b1e1f0" />
<img width="386" height="20" alt="imagen" src="https://github.com/user-attachments/assets/c9d09f2f-a3af-4a4c-87ab-d9220d90931a" />

3.2. Puertos en escucha

<img width="948" height="58" alt="imagen" src="https://github.com/user-attachments/assets/c4580288-0fd0-43bf-9387-62178d205b36" />

3.3. Prueba desde el terminal y desde el navegador
<img width="959" height="227" alt="imagen" src="https://github.com/user-attachments/assets/063a93c3-73d3-43be-be5d-73c262b61fc5" />
**Captura obligatoria**
<img width="929" height="800" alt="imagen" src="https://github.com/user-attachments/assets/88c46a80-f03f-4ec8-8a72-f9a7cdb3da26" />

3.4. Firewall (si está activo)

<img width="360" height="109" alt="imagen" src="https://github.com/user-attachments/assets/29e5ee8a-a775-44f7-9231-55fcb09de590" />

**PREGUNTA 2:¿Qué diferencia hay entre los perfiles Apache, Apache Full y Apache Secure?**

Apache:instalacion basica 

Apache full: se instala apache con mas modulos y funciones

Apache secure: configuracion orientada en HTTPS y seguridad

**Apartado 4. Comandos principales de administración**

| Comando | Función |
| :--- | :--- |¿Por qué Apache usa enlaces simbólicos entre los directorios *-available y *-enabled?
| `sudo systemctl start apache2` | Inicia el servicio |
| `sudo systemctl stop apache2` | Detiene el servicio |
| `sudo systemctl restart apache2` | Reinicia (corta conexiones) |
| `sudo systemctl reload apache2` | Recarga la configuración sin cortar conexiones |
| `sudo systemctl enable apache2` | Arranque automático al iniciar el sistema |
| `sudo systemctl disable apache2` | Desactiva el arranque automático |
| `apache2ctl configtest` | Comprueba la sintaxis de la configuración |
| `apache2ctl -S` | Muestra los sitios (virtual hosts) cargados |
| `apache2ctl -M` | Lista los módulos cargados |
| `a2enmod` / `a2dismod` | Activa / desactiva módulos |
| `a2ensite` / `a2dissite` | Activa / desactiva sitios |
| `a2enconf` / `a2disconf` | Activa / desactiva fragmentos de configuración |

<img width="953" height="531" alt="Captura de 2026-10-07 10-19-13" src="https://github.com/user-attachments/assets/ddb78b2b-cfe9-4aa0-a124-f25c7d077806" />
<img width="427" height="266" alt="imagen" src="https://github.com/user-attachments/assets/858cdb53-32fd-47ad-b1e4-ea5d2d86887a" />

**PREGUNTA 3:¿Cuándo conviene usar reload en lugar de restart?**

Conviene usar reload en lugar de restart cuando realizas cambios menores de configuración (como añadir un nuevo Virtual Host, cambiar un parámetro o activar/desactivar un sitio web) y deseas aplicar los cambios sin interrumpir las conexiones activas de los usuarios.

**Apartado 5. Ficheros y directorios importantes**

| Ruta | Descripción |
| :--- | :--- |
| `/etc/apache2/apache2.conf` | Es el archivo de configuración global de Apache donde se define el comportamiento general del servidor. |
| `/etc/apache2/ports.conf` | Aquí se indican los puertos de red por los que Apache va a escuchar las peticiones (por defecto el 80 y 443). |
| `/etc/apache2/sites-available/` | Carpeta donde se guardan las configuraciones de todas las webs que he creado, estén o no publicadas. |
| `/etc/apache2/sites-enabled/` | Contiene los accesos directos a las webs de `sites-available` que están actualmente activas y visibles. |
| `/etc/apache2/mods-available/` y `mods-enabled/` | En estas carpetas se guardan los módulos extras de Apache; en `available` los instalados y en `enabled` los activados. |
| `/etc/apache2/conf-available/` y `conf-enabled/` | Sirve para guardar y activar bloques de configuración adicionales o globales que no son webs completas. |
| `/etc/apache2/envvars` | Fichero donde se definen las variables de sistema que usará Apache (como el usuario y grupo con el que se ejecuta). |
| `/var/www/html/` | Es la carpeta raíz principal donde se suben los archivos de la web (HTML, PHP, imágenes, etc.). |
| `/var/log/apache2/access.log` | Archivo de registro donde quedan guardadas todas las visitas y peticiones que recibe el servidor. |
| `/var/log/apache2/error.log` | Archivo de registro donde se guardan los fallos y errores que ocurren en la web o en el servidor. |

**Captura obligaoria de /etc/apache2/.**

<img width="513" height="201" alt="imagen" src="https://github.com/user-attachments/assets/461dd2ad-e854-41e7-9680-de9ae895809f" />

**PREGUNTA 4:¿Por qué Apache usa enlaces simbólicos entre los directorios**: *-available y *-enabled?

por organización, modularidad y seguridad.

**Apartado 6. Modificaciones típicas del servicio**

Haz siempre una copia de seguridad antes de modificar un fichero:
<img width="653" height="62" alt="imagen" src="https://github.com/user-attachments/assets/3b3b8ea3-df3d-4674-a12c-00bcf34ab8ef" />

**6.1. Cambiar la página de inicio**
<img width="594" height="38" alt="imagen" src="https://github.com/user-attachments/assets/dace95e7-a208-4d8d-9325-d24b3e0d17c1" />

**6.2. Cambiar el puerto de escucha** (por ejemplo, al 8080)

Edita /etc/apache2/ports.conf y el VirtualHost de 000-default.conf:
<img width="948" height="239" alt="imagen" src="https://github.com/user-attachments/assets/42e34392-2aa2-459d-b841-940b0ec0fcc5" />

Cambia Listen 80 por Listen 8080 y <VirtualHost *:80> por <VirtualHost *:8080>.
<img width="950" height="427" alt="imagen" src="https://github.com/user-attachments/assets/fddd24e1-1b1c-414a-900f-2ec145d795d0" />

**6.3. Definir el nombre del servidor** (elimina el aviso "Could not reliably determine the server's fully qualified domain name")

<img width="809" height="113" alt="imagen" src="https://github.com/user-attachments/assets/b6080f51-60a0-4034-9714-3d61f4280871" />

**6.4. Cambiar el correo del administrador** (ServerAdmin en el fichero del sitio).

<img width="945" height="331" alt="imagen" src="https://github.com/user-attachments/assets/d68cd06f-a734-4c36-8df9-08f9affd9470" />
