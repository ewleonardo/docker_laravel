# Passo a Passo: Setup Docker para Projetos Laravel

Nesta base de passo a passo, você aprenderá como desenvolver um projeto Laravel com Docker. Siga as etapas abaixo para obter sucesso.

## 1º Passo - Instalação das Ferramentas

**🟢 Instale o laravel na versão desejada:**

-   [Instalação do laravel](https://laravel.com/docs/master#your-first-laravel-project)
-   Observação: Você deve saber qual a versão do _Laravel_ o Projeto vai usar. Você também deve saber em qual versão do _PHP_ o Projeto funciona de acordo com a versão do _Laravel_.

**🟢 Instale o docker e o docker-compose:**

-   [Instalação do docker](https://docs.docker.com/get-docker/).
-   [Instalação do docker-compose](https://docs.docker.com/compose/install/).

**🟢 Instale o git:**

-   [Instalação do Git](https://github.com/git-guides/install-git).
-   Observação: Nesse método precisaremos usar o [`git clone`](https://docs.github.com/pt/repositories/creating-and-managing-repositories/cloning-a-repository).

## 2º Passo - Setup do _docker_ no projeto _laravel_

**🟢 Instale(ou clone) o projeto laravel**

-   [Via composer](https://www.diegobrocanelli.com.br/mysql/comandos-basicos-mysql-no-terminal/);
-   [Via git clone](https://github.com/laravel/laravel).

**🟢 Clone o repositório do setup**

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

**🟢 Suba os containers do projeto**

-   Observação: Execute os comandos abaixo apenas quando o projeto já estiver com a configuração docker dentro dele.

Subir containers

```sh
docker-compose up -d
```

Remova os containers

```sh
docker-compose down -v
```

**🟢 Comandos úteis para os containers**

Para acessar um container do projeto por terminal/bash.

```sh
docker-compose exec app bash
```

Para acessar o container do mysql por terminal.

```sh
docker exec -it testecamaragibepegovbr_db_1 mysql -uroot -p
```

## 3º Passo - Conclusão

**Parabéns!**
Provavelmente, após seguir este passo a passo, você conseguiu subir seu projeto _laravel_ utilizando _docker_!. Certifique-se de verificar se tudo foi feito corretamente e aproveite os resultados.

Acessar o projeto
[http://localhost:8989](http://localhost:8989)

## Dicas, sites e documentações

**🟢 Documentações:**

    - [Laravel](https://laravel.com/);
    - [Docker](https://docs.docker.com/);
    - [Git](https://docs.github.com/pt).

**🟢 Sites**

    - [Comandos Básico MySQL](https://www.diegobrocanelli.com.br/mysql/comandos-basicos-mysql-no-terminal/);

## Referências

-   _Observação:_ Nos recursos abaixo, se trás as versões 10, 9 e 8 do laravel, mas o método pode ser utilizado para as demais versões mudando a versão do php usado.
-   [Vídeo - Carlos Ferreira Laravel 10 (feat. Docker)](https://www.youtube.com/watch?v=oz9K3jtFUvI)
-   [Repositório](https://github.com/especializati/setup-docker-laravel.git)
