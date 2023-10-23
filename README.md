<p align="center">
    <a href="https://git-scm.com/doc" target="_blank"><img src="https://skillicons.dev/icons?i=git" /></a>
    <a a href="https://docs.docker.com/"><img src="https://skillicons.dev/icons?i=docker" /></a>
    <a href="https://laravel.com/docs/master"><img src="https://skillicons.dev/icons?i=laravel" /></a>
</p>

<div align=center>

## Setup Linux 🐧

</div>

<div align=center>

### 1️⃣ Instalação das Ferramentas! 🔧

</div>

<!-- ##### Instalação do Laravel 🔹

-   [Via Composer](https://laravel.com/docs/master#your-first-laravel-project)
-   [Via Git Clone](https://github.com/laravel/laravel) -->

🔹 Instalação do Docker

```sh
sudo apt install docker* -y
```

🔹 Instalação do docker-compose

```sh
sudo apt install docker-compose
```

🔹 Instalação do Git

```sh
sudo apt install git-all
```

> [!IMPORTANT]
> A instalação das ferramentas é crucial para o desenvolvimento do projeto Docker + Laravel.

<br>

<div align=center>

### 2️⃣ Criando o Projeto Laravel!

</div>

🔹 Criação do Projeto Laravel
> Pode ser feita "via composer" ou via "git clone"

1. [Instalação do Laravel](https://github.com/ewleonardo/docker_laravel/tree/main#instala%C3%A7%C3%A3o-do-laravel-)

##### Dockerizando o projeto 🔹

1. [Instalação do Docker](https://github.com/ewleonardo/docker_laravel/tree/main#instala%C3%A7%C3%A3o-do-docker-).
2. Clone o repositório das configurações docker para sua máquina.

    ```sh
    git clone https://github.com/ewleonardo/docker_laravel.git
    ```

3. Após o fim da clonagem. Cópie todos os arquivos e diretórios para a raiz do seu projeto.

    ```sh
    cp -rf docker_laravel/* <nome_do_projeto>/
    ```

4. Se não houver, crie o arquivo **".env"**. _(OPCIONAL)_

    ```sh
    cp .env.example .env
    ```

5. Atualize as variáveis de ambiente do arquivo local **".env"** pelas seguintes informações.

    ```
    APP_NAME="nome_do_projeto"
    APP_URL=http://localhost:8989

    DB_CONNECTION=mysql
    DB_HOST=db              // Nome do container do banco de dados.
    DB_PORT=3306
    DB_DATABASE=laravel
    DB_USERNAME=root
    DB_PASSWORD=root

    CACHE_DRIVER=redis
    QUEUE_CONNECTION=redis
    SESSION_DRIVER=redis

    REDIS_HOST=redis
    REDIS_PASSWORD=null
    REDIS_PORT=6379
    ```

6. Iniciar os serviços do docker-compose.

    ```sh
    docker compose up -d
    ```

7. Entrar no container da aplicação.

    ```sh
    docker compose exec app bash
    ```

8. Dentro do container app. Instalar dependências do projeto e gerar chave **"APP_KEY"** do **".env"**.

    ```sh
    composer install
    ```

    ```sh
    php artisan key:generate
    ```

9. Acessar o projeto
   [http://localhost:8989](http://localhost:8989)

##### Interação com os Containers 🔹

1.  Acessar terminal dos containers.

    ```sh
    docker compose exec <nome_do_container> bash
    ```

2.  Acessar diretamente o mysql de um container via terminal.

    ```sh
    docker exec -it <container_id ou nome_do_container> mysql -uroot -p
    ```

3.  Iniciar serviços docker-compose / Remover os serviços do docker-compose.
    ```sh
    docker compose up -d
    ```
    ```sh
    docker compose down -v
    ```
4.  Buildar a imagem. (No caso de alterações da configuração docker)
    ```sh
    docker compose build
    ```
    | OR
    ```sh
    docker compose up --build
    ```
5.  Colocar arquivos dentro dos containers / Pegar arquivos dos Containers.
    ```sh
    docker cp <nome_do_arquivo> <nome_do_container ou id_do_container>:/<pasta_do_container>
    ```
    ```sh
    docker cp <id_do_container>:/<nome_do_arquivo> meuarquivo.js
    ```

### 3️⃣ Dicas e Precauções

##### Interação com os Containers 🔹

1. [Comandos no bash MySQL](https://www.diegobrocanelli.com.br/mysql/comandos-basicos-mysql-no-terminal/);

##### Interação com os Containers 🔹

1. [Corrigir importação de muitos registros](https://pt.stackoverflow.com/questions/37520/erro-1153-do-mysql-got-a-packet-bigger-than-max-allowed-packet-bytes);

### 4️⃣ Documentações e Fontes

##### Documentações 🔹

1. [Laravel](https://laravel.com/)

2. [Docker](https://docs.docker.com/)

3. [Git](https://docs.github.com/pt)

##### Fontes 🔹

1. [Video Yt](https://www.youtube.com/watch?v=oz9K3jtFUvI)

2. [Repositório](https://github.com/especializati/setup-docker-laravel.git)
