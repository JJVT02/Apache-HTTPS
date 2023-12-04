# Apache-HTTPS
## Creamos nuestro propio dominio
### Paso 1: Registro en No-IP
Ir al Sitio Web de No-IP: Accede al sitio web de No-IP (https://www.noip.com/).

Registro de Cuenta: Si aún no tienes una cuenta, regístrate en el sitio web proporcionando la información necesaria.
![](/img/paginaNO-IP.png)
### Paso 2: Crear un Nuevo Host (Dominio)
Iniciar Sesión: Inicia sesión en tu cuenta de No-IP con las credenciales que proporcionaste durante el registro.

Dashboard (Panel de Control): Después de iniciar sesión, deberías ver un panel de control o dashboard.

Agregar Nuevo Host: Busca una opción como "Add a Host" o "Create a Host" en el panel de control.
![](/img/creamos.png)
### Paso 3: Configuración del Nuevo Host
Seleccionar un Dominio: Elige un nombre de dominio que desees para tu host. 
Puedes elegir un subdominio de los dominios proporcionados por No-IP.

Seleccionar el Tipo de Host: Especifica el tipo de host que estás configurando. Por ejemplo, podrías seleccionar "DNS Host (A)".

Dirección IP: Si tu dirección IP es dinámica, No-IP puede detectarla automáticamente. De lo contrario, proporciona tu dirección IP actual.

TTL (Time to Live): Establece el valor de TTL, que determina durante cuánto tiempo se almacenará en caché la información del dominio en otros servidores DNS.

Agregar Host: Haz clic en el botón para agregar o crear el host.

![](/img/ipyhost.png)
## Instalar y configurar el cliente.

Realizamos la instalación y actualización de snapd.
```bash
sudo apt install snapd
sudo snap install core
sudo snap refresh core
```
![imagen de instalacion snap](/img/snapd.png)
![instalacion core](/img/core.png)

Eliminamos si existiese alguna instalación previa de certbot con apt.

```bash
sudo apt remove certbot -y
```

Instalamos el cliente de Certbot con snapd.
```bash
sudo snap install --classic certbot
```
![](/img/classic.png)

Creamos una alias para el comando certbot.
```bash
sudo ln -fs /snap/bin/certbot /usr/bin/certbot
```
![](/img/ln.png)

Obtenemos el certificado y configuramos el servidor web Apache.
```bash
sudo certbot --apache
```
![](/img/certbot.png)


# Dentro de la configuracion

![](/img/configuracion1.png)
![](/img/configuracion2.png)


## Creacion del certificado
![](/img/certificado.png)