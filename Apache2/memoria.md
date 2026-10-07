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
| :--- | :--- |
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
