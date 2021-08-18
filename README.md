# Docker Laravel 8

Um simples workflow do Docker Compose que seta um LEMP (Linux, NGINX, MySQL, PHP) para um ambiente local de desenvolvimento com Laravel 8.

## Portas

Ports used in the project:
| Software | Port |
|-------------- | -------------- |
| **nginx** | 80 |
| **adminer** | 8080 |
| **mysql** | 3306 |
| **php** | 9000 |

## Uso

Para usar esse workflow, você precisa ter o [Docker instalado](https://docs.docker.com/) e o [Docker Compose](https://docs.docker.com/compose/install/). Depois disso, você pode clonar este repositório.

1. Clone this project:

   ```sh
   git clone https://github.com/bymatheus/php8-laravel8-docker-environment
   ```

2. Você pode copiar os dados clonados para a raiz do seu projeto Laravel. Só tome cuidado com o `.gitignore` e para não copiar o `diretório do git` deste repositório. 

3. Build o worflow com o comando:

   ```sh
   docker compose build 
   ```

4. Rode o worflow com o comando:

   ```sh
   docker compose up
   ```

---

## PHP
Você pode alterar a configuração do PHP. O Arquivo customizado está no diretório `./docker/php/config/custom.ini`

---

## Remember

Atualize a configuração do banco de dados no `docker-compose.yml` e no seu arquivo `.env`.

```dotenv
# .env
DB_CONNECTION=mysql
DB_HOST=mysql # Nome do container
DB_PORT=3306 # Porta do MYSQL
DB_DATABASE=db_name # Nome da database
DB_USERNAME=db_user # Nome do usuário do banco de dados
DB_PASSWORD=db_password # Senha do banco de dados
```

```yaml
# .docker-compose.yml
MYSQL_DATABASE: db_name
MYSQL_USER: db_user
MYSQL_PASSWORD: db_password
MYSQL_ROOT_PASSWORD: db_root_password
```

---

## Comandos especiais

Para desativar o compose:

```sh
docker compose down
```

Comandos Composer (ex: update)

```sh
docker compose run --rm composer update
```

Comandos npm (ex: install)

```sh
docker compose run --rm npm install
```

Comandos artisan (ex: migrate)

```sh
docker compose run --rm artisan migrate
```
