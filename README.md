# Infraestructura Nube Resiliente - Nextcloud + Keycloak

Este proyecto despliega una nube privada segura con Nextcloud, base de datos PostgreSQL, caché en Redis y un Proxy Inverso Nginx.

## 🚀 Instrucciones de Despliegue

### 1. Requisitos Previos
- Docker y Docker Compose instalados.
- Servidor Linux (Ubuntu/Debian preferiblemente).

### 2. Configuración de Seguridad (Secrets)
Para proteger las credenciales, este proyecto usa Docker Secrets. Antes de iniciar, debe crear la carpeta de secretos y los archivos necesarios:

```bash
# Crear directorio
mkdir -p secrets

# Crear las credenciales (Reemplace con sus propias claves)
echo "tu_password_db" > secrets/db_password.txt
echo "admin_username" > secrets/admin_user.txt
echo "admin_password" > secrets/admin_pass.txt
```
### 3. Lanzamiento
Una vez creados los secretos y configurado el archivo nginx.conf, ejecute:
```bash
docker-compose up -d
```
### 4. Arquitectura
Una vez creados los secretos y configurado el archivo nginx.conf, ejecute:
```bash
Nginx: Proxy Inverso (Puerto 80).
Nextcloud: Aplicación principal.
PostgreSQL: Base de datos persistente.
Redis: Manejador de memoria y caché.
Keycloak: Gestión de Identidades (IAM).
```
