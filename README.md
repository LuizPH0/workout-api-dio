# Projeto
## WorkoutAPI

Esta é uma API de competição de crossfit chamada WorkoutAPI. É uma API pequena, devido a ser um projeto mais hands-on e simplificado onde foi desenvolvido uma API de poucas tabelas, mas seguindo os fundamentos da FastAPI.

## Modelagem de entidade e relacionamento - MER
![MER](/mer.jpg "Modelagem de entidade e relacionamento")

## Stack da API

A API foi desenvolvida utilizando o `fastapi` (async), junto das seguintes libs: `alembic`, `SQLAlchemy`, `pydantic`. Para salvar os dados está sendo utilizando o `postgres` por meio do `docker`.

## Execução da API

Para executar o projeto, utilizei a venv com a versão 3.12 do `python` para o ambiente virtual.

Caso opte por usar venv, execute:

```
python -m venv venv
.\venv\Scripts\activate
pip install -r requirements.txt
```

Para subir o banco de dados, caso não tenha o [docker](https://www.docker.com/products/docker-desktop/) instalado, faça a instalação e logo em seguida, execute:

```bash
docker-compose up
```

Para criar uma nova migration, execute:

```bash
make create-migrations d="nome_da_migration"
```

Para criar o banco de dados, execute:

```bash
make run-migrations
```
## API

Para subir a API, execute:
```bash
make run
```
e acesse: http://127.0.0.1:8000/docs

## Algumas implementações
    - CRUD completo para todas entidades;
    - Implementação de query parameters nos endpoints;
        - atleta
            - nome
            - cpf
    - Response customizada de retorno de endpoints;
        - get all
            - atleta
                - nome
                - categoria
                - centro_treinamento
    - Manipulação de exceção de integridade dos dados em cada módulo/tabela;
        - sqlalchemy.exc.IntegrityError devolve a seguinte mensagem: “Já existe um atleta cadastrado com o cpf: x”
            - o mesmo para categorias e centros de treinamento
        - status_code: 303
    - Paginação utilizando a lib: fastapi-pagination;
        - limit e offset

## TODO
    - Implementar query parameters para os outros módulos;
        - categorias
        - centro_treinamento
    - Testes
        - unit tests
        - use case tests
        - integration tests

# Referências

FastAPI: https://fastapi.tiangolo.com/

Pydantic: https://docs.pydantic.dev/latest/

SQLAlchemy: https://docs.sqlalchemy.org/en/20/

Alembic: https://alembic.sqlalchemy.org/en/latest/

Fastapi-pagination: https://uriyyo-fastapi-pagination.netlify.app/


# Connect with me

[![Github Badge](https://img.shields.io/badge/-Github-000?style=flat-square&logo=Github&logoColor=white&link=https://github.com/zawarudobngdev)](https://github.com/zawarudobngdev)
[![Linkedin Badge](https://img.shields.io/badge/-LinkedIn-blue?style=flat-square&logo=Linkedin&logoColor=white&link=https://www.linkedin.com/in/murilo-meranca/)](https://www.linkedin.com/in/murilo-meranca/)
[![Whatsapp Badge](https://img.shields.io/badge/-Whatsapp-4CA143?style=flat-square&labelColor=4CA143&logo=whatsapp&logoColor=white&link=https://api.whatsapp.com/send?phone=5518998075351&text=Hello!)](https://api.whatsapp.com/send?phone=5518998075351&text=Hello!)
[![Email Badge](https://img.shields.io/badge/-Email-c14438?style=flat-square&logo=microsoft-outlook&logoColor=white&link=mailto:murilo.m@hotmail.com)](mailto:murilo.m@hotmail.com)

<img width="25%" height="25%" src="https://github.com/zawarudobngdev/zawarudobngdev/blob/master/dog.png">
