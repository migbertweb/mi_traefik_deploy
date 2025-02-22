# my traefik deploy

<!--toc:start-->

- [mytraefik_deploy](#mytraefikdeploy)
- [Pasos Iniciales](#pasos-iniciales)
- [crear esta red docker antes de correr el servicio](#crear-esta-red-docker-antes-de-correr-el-servicio)
- [crear los archivos para los certificados](#crear-los-archivos-para-los-certificados)
- [crear el archivo con las credenciales para autenticacion basic_auth_credentials](#crear-el-archivo-con-las-credenciales-para-autenticacion-basicauthcredentials)
- [Iniciar el servicio](#iniciar-el-servicio)
<!--toc:end-->

### Pasos Iniciales

- clone el repositorio
- cp env_example .env y modifiquelo segun se requiere

### crear esta red docker antes de correr el servicio

```bash
docker network create traefik-servicenet
```

### crear los archivos para los certificados

```bash
touch ./datos/acme-cloudflare.json
touch ./datos/acme.json
chmod 600 ./datos/*.json
```

### crear el archivo con las credenciales para autenticacion basic_auth_credentials

```bash
sudo apt update
sudo apt install apache2-utils
htpasswd -cB basic_auth_credentials usuario
```

cambiar usuario por el nombre de usuario correcto

### Iniciar el servicio

```bash
docker compose up -d
```
