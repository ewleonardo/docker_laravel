# Passo a Passo: Setup Docker para Projetos Laravel

-- Nesta base de passo a passo, você aprenderá como desenvolver um projeto Laravel utilizando Docker. Siga as etapas abaixo para obter sucesso no setup.

## Setup Linux 🐧

### 1️⃣ Instalação

##### Instalação do Laravel 🔹

-   [Via Composer](https://laravel.com/docs/master#your-first-laravel-project)
-   [Via Git Clone](https://github.com/laravel/laravel)

##### Instalação do Docker 🔹

-   [Docker](https://docs.docker.com/desktop/install/linux-install/)
    ```sh
    sudo apt install docker
    ```
-   [docker-compose](https://docs.docker.com/compose/install/).
    ```sh
    sudo apt install docker-compose
    ```

##### Instalação do Git 🔹

-   [Instalação do Git](https://github.com/git-guides/install-git).
    ```sh
    sudo apt install git-all
    ```

### 2️⃣ Montagem do Ambiente

##### Criação do projeto 🔹

**_Instale(ou clone) o projeto laravel_**

1. [Instalação do Laravel]()

##### Dockerizando o projeto 🔹

1. [Instalação do Docker]().
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
    docker-compose up -d
    ```

7. Instalar dependências do projeto e gerar chave **"APP_KEY"** do **".env"**.

    ```sh
    docker-compose exec <container_id ou nome_do_container> bash
    ```

    ```sh
    composer install
    ```

    ```sh
    php artisan key:generate
    ```

8. Acessar o projeto
   [http://localhost:8989](http://localhost:8989)

##### Interação com os Containers 🔹

1. Acessar containers via terminal.

    ```sh
    docker-compose exec <container_id ou nome_do_container> bash
    ```

2. Acessar diretamente o mysql de um container via terminal.

    ```sh
    docker exec -it <container_id ou nome_do_container> mysql -uroot -p
    ```

3. Iniciar serviços docker-compose / Remover os serviços do docker-compose.
    ```sh
    docker-compose up -d
    ```
    ```sh
    docker-compose down -v
    ```
4. Buildar a imagem. (No caso de alterações da configuração docker)
    ```sh
    docker-compose build
    ```
    | OR
    ```sh
    docker-compose up --build
    ```

### 3️⃣ Dicas e Precauções

##### Interação com os Containers 🔹

1. [Comandos no bash MySQL](https://www.diegobrocanelli.com.br/mysql/comandos-basicos-mysql-no-terminal/);

### 4️⃣ Documentações e Fontes

##### -- [Laravel](https://laravel.com/)

##### -- [Docker](https://docs.docker.com/)

##### -- [Git](https://docs.github.com/pt)

##### -- [Video Yt](https://www.youtube.com/watch?v=oz9K3jtFUvI)

##### -- [Repositório](https://github.com/especializati/setup-docker-laravel.git)
