<p align="center">
    <a href="https://git-scm.com/doc" target="_blank"><img src="https://skillicons.dev/icons?i=git" /></a>
    <a a href="https://docs.docker.com/"><img src="https://skillicons.dev/icons?i=docker" /></a>
    <a href="https://laravel.com/docs/master"><img src="https://skillicons.dev/icons?i=laravel" /></a>
</p>

<div align=center>

<br>

## 🐧 Setup Linux 🐧

</div>

<div align=center>

### 1️⃣ Instalação das Ferramentas! 🔧

</div>

🔹 Instalação do Docker ⤵

```sh
sudo apt install docker* -y
```

<br>

🔹 Instalação do docker-compose ⤵

```sh
sudo apt install docker-compose
```

<br>

🔹 Instalação do Git ⤵

```sh
sudo apt install git-all
```

> [!IMPORTANT]
> A instalação das ferramentas é CRUCIAL para o desenvolvimento do projeto Docker + Laravel.

<br>

<div align=center>

### 2️⃣ Criando o Projeto Laravel! 🆕

</div>

🔹 Criação do Projeto Laravel (Via Composer) ⤵

```sh
composer create-project laravel/laravel example-app
```

> [!NOTE]
> Instale seu Projeto Laravel de acordo com a versão desejada. [(Documentação Laravel)](https://laravel.com/docs/master/installation#your-first-laravel-project).

<br>

🔹 Criação do Projeto Laravel (Via Git Clone) ⤵

```sh
git clone https://github.com/laravel/laravel.git
```

> [!NOTE]
> Instale seu Projeto Laravel de acordo com a versão desejada. [(Repositório Git do Laravel)](https://github.com/laravel/laravel/tree/10.x).

<br>

```sh
cp .env.example .env
```

> [!NOTE]
> Use este comando para criar o arquivo .ENV dentro do projeto.

<br>

<div align=center>
    
### 3️⃣ Adicionando configurações Docker no seu projeto Laravel! ⚙️

</div>

🔹 Clone o repositório para sua máquina (Via Git Clone) ⤵

```sh
git clone https://github.com/ewleonardo/docker_laravel.git
```

<br>

🔹 Copie os itens dentro da pasta "docker_laravel" para seu projeto Laravel ⤵

```sh
cp -rf docker_laravel/* nome_do_projeto/
```

<br>

🔹 Atualize as variáveis de ambiente do arquivo local **".ENV"** pelas seguintes informações. ⤵

```laravel
APP_NAME="nome_do_projeto"
APP_URL=http://localhost:8989

DB_CONNECTION=mysql
DB_HOST=db
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

<br>

🔹 Agora você já pode iniciar os containers do docker-compose. (Com parâmetro "-d") ⤵

```sh
docker compose up -d
```

> [!IMPORTANT]
> Antes de iniciar os containers, verifique se a versão do PHP corresponde com a do Laravel.

<br>

<div align=center>
    
### 4️⃣ Configurações finais do projeto! 🏁

</div>

🔹 Entre no bash/terminal do container onde está o projeto Laravel! ⤵

```sh
docker compose exec app bash
```

🔹 Instale as dependências do seu projeto! ⤵

```sh
composer install
```

```sh
php artisan key:generate
```

> [!NOTE]
> Execute os comandos acima dentro do bash/terminal do container onde está o projeto Laravel!.

<br>

🔹 Acesse o seu projeto ⤵

> [http://localhost:8989](http://localhost:8989)

<br>

<!-- <div align=center>

### 5️⃣ Comandos para manipulação dos containers!

</div>

🔹 Iniciar containers docker-compose ⤵

```sh
docker compose up -d
```

<br>

🔹 Parar containers docker-compose ⤵

```sh
docker compose down -v
```

> [!NOTE]
> Caso queira manter o volume, apague o parâmetro "-v" do comando.

<br>

<div align=center>

### 6️⃣ Recursos Adicionais!
</div> -->

<hr>
    
<!--

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

2. [Repositório](https://github.com/especializati/setup-docker-laravel.git) -->
