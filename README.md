# Passo a Passo: Setup Docker para Projetos Laravel

Nesta base de passo a passo, você aprenderá como desenvolver um projeto Laravel com Docker. Siga as etapas abaixo para obter sucesso.

## 1º Passo: Instalação das Ferramentas

**Instale o laravel na versão desejada:**

- [Instalação do laravel](https://laravel.com/docs/master#your-first-laravel-project)
- Observação: Você deve saber qual a versão do _Laravel_ o Projeto vai usar. Você também deve saber em qual versão do _PHP_ o Projeto funciona de acordo com a versão do _Laravel_.

2. **Instale o docker e o docker-compose:**

    - SubPasso 1: [Instalação do docker](https://docs.docker.com/get-docker/).
    - SubPasso 2: [Instalação do docker-compose](https://docs.docker.com/compose/install/).

3. **Instale o git:**

    - SubPasso 1: [Instalação do Git](https://github.com/git-guides/install-git).
        - Obs 2: Nessa ferramenta precisaremos usar o [`git clone`](https://docs.github.com/pt/repositories/creating-and-managing-repositories/cloning-a-repository).

## Passo 2: Setup do _docker_ no projeto _laravel_

1.  **Instale(ou clone) o projeto laravel**

    -   Formas de Instalação:
        -   [composer](https://www.diegobrocanelli.com.br/mysql/comandos-basicos-mysql-no-terminal/);
        -   [github](https://github.com/laravel/laravel).

2.  **Clone o repositório do setup**

-   Clone o repositório que contém as configurações docker e docker-compose

```sh
git clone https://github.com/ewleonardo/docker_laravel
```

-   Após o fim da clonagem. Cópie todos os arquivos e diretórios para a raiz do seu projeto.

```sh
cp -rf docker-laravel/* nome-projeto/
```

-   Atualize as seguintes variáveis de ambiente do arquivo .env do seu projeto laravel

```dosini
APP_NAME="Nome_do_projeto"
APP_URL=http://localhost:8989

DB_CONNECTION=mysql
DB_HOST=db              // NAME do container com o banco de dados
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

3. **Suba os containers do projeto**

    - OBS: Execute os comandos dentro do projeto já configurado

Subir containers

```sh
docker-compose up -d
```

Remova os containers

```sh
docker-compose down -v
```

4.  **Comandos úteis para os containers**

Para acessar o container do projeto por terminal.

```sh
    docker-compose exec app bash
```

Para acessar o container do mysql por terminal.

```sh
    docker exec -it testecamaragibepegovbr_db_1 mysql -uroot -p
```

Acessar o projeto
[http://localhost:8989](http://localhost:8989)

## Dicas, sites e documentações

1. **Documentações:**

    - [Laravel](https://laravel.com/);
    - [Docker](https://docs.docker.com/);
    - [Git](https://docs.github.com/pt).

2. **Sites**

    - [Comandos Básico MySQL](https://www.diegobrocanelli.com.br/mysql/comandos-basicos-mysql-no-terminal/);

## Conclusão

**Parabéns!**
Provavelmente, após seguir este passo a passo, você conseguiu subir seu projeto _laravel_ utilizando _docker_!. Certifique-se de verificar se tudo foi feito corretamente e aproveite os resultados.

## Referências

-   [Vídeo - Carlos Ferreira Laravel 10 (feat. Docker)](https://www.youtube.com/watch?v=oz9K3jtFUvI)
-   [Repositório](https://github.com/especializati/setup-docker-laravel.git)
-   **OBS:** No vídeo temos versão 10, 9 e 8 mas o método pode ser utilizado para outras versões fazendo algumas alterações na versão _php_ do _dockerfile_.
