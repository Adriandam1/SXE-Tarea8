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

### Añadiendo imagenes pendientes descripcion:

![wordpress1_instalar](https://github.com/user-attachments/assets/bee633be-b0c7-48eb-8c7f-f49a4ff11829)

![wordpress2_instalar2](https://github.com/user-attachments/assets/ec856a79-1220-4e28-9928-cfb5724e3cfc)

![Wordpress3_bienvenida](https://github.com/user-attachments/assets/99ac5a69-e786-45f3-925f-a0cbd9b46496)

![wordpress4_temas](https://github.com/user-attachments/assets/c457790c-5248-4e12-9498-81e8f9ba3732)

![wordpress5_temas2](https://github.com/user-attachments/assets/b68b281d-5139-4b62-940b-7d3cea9dfb51)

![wordpress6_temas3](https://github.com/user-attachments/assets/4f04a054-c12f-4b6f-831f-c852ca3bca28)

![wordpress7_usuario1](https://github.com/user-attachments/assets/0fa31f83-4cb5-411e-b802-5680f074fea6)

![wordpress8_usuario2](https://github.com/user-attachments/assets/5d23c533-3cbb-4795-a06e-ae19156f587a)










-----------------------------------------------------





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








