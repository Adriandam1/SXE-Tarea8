# SXE-Tarea8

```bash
mkdir carpetaWordPress
```
(nos situamos en la carpeta)

```bash
sudo nano docker-compose.yml
```
## Creamos nuestro docker-compose.yml
```bash
services:
  db:
    image: mariadb:10.6.4-focal
    command: '--default-authentication-plugin=mysql_native_password'
    volumes:
      - ./db_data:/var/lib/mysql
    ports:
      - 3306:3306
    restart: no
    environment:
      - MYSQL_ROOT_PASSWORD=wordpress
      - MYSQL_DATABASE=wordpress_db
      - MYSQL_USER=wordpress
      - MYSQL_PASSWORD=wordpress

  wordpress:
    image: wordpress:latest
    volumes:
      - ./wp_data:/var/www/html
    ports:
      - 8080:80
    restart: no
    environment:
      - WORDPRESS_DB_HOST=db
      - WORDPRESS_DB_USER=wordpress
      - WORDPRESS_DB_PASSWORD=wordpress
      - WORDPRESS_DB_NAME=wordpress_db

volumes:
  db_data:
  wp_data:

```

### ----------------------Pendientes comprobaciones clase------------------------------------------------

## Cambia el tema predeterminado de WordPress e instala un tema diferente (puede ser cualquiera). Explora las opciones de personalización que ofrece y evalúa cómo afecta al contenido.
Hay que ir a pandel de administración a "apariencia" y "temas"

## Crea usuarios con diferentes roles: al menos un editor, un colaborador y un autor.
Hay que ir a panel de administación, usuarios.

## Pendiente comprobaciones compañeros










### Bibliografía (enlaces)

[https://codex.wordpress.org/es:Roles_y_Capacidades/](https://codex.wordpress.org/es:Roles_y_Capacidades
)

[https://wordpress.org/documentation/article/work-with-themes/](https://wordpress.org/documentation/article/work-with-themes/)

**GitHub docker con wordpress**

[https://github.com/docker/awesome-compose/tree/master/official-documentation-samples/wordpress/](https://github.com/docker/awesome-compose/tree/master/official-documentation-samples/wordpress/)

**Consejos varios de mi amigo Jesus (experto en servidores y docker)**








