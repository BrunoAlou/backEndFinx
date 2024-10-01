## Instalação

### Docker

Caso possua Docker em sua máquina, utilize o seguinte comando para rodar nossa API de mock:

```bash
docker-compose up
```

### Pacote NPM

Se preferir, também é possível rodar a API de mock diretamente pela sua máquina:

```bash
npm install -g json-server
cd config
json-server --watch db.json
```

## Mock API

Com o serviço executando, você poderá utilizar as seguintes APIs:

### Data

Listagem de consultas registradas em `data`:

`GET http://0.0.0.0:8080/data`

### Exemplos de Payload

#### Request

```json
GET http://0.0.0.0:8080/data
```

#### Response

```json
[
    {
        "id": 1,
        "medico": {
            "nome": "Afonso Silva"
        },
        "paciente": {
            "nome": "Gustavo Santos",
            "dataNascimento": "2023-08-21"
        },
        "dataCriacao": "2024-09-20T12:00:00Z"
    },
    {
        "id": 2,
        "medico": {
            "nome": "Fernando Santos"
        },
        "paciente": {
            "nome": "Jurandir Santos",
            "dataNascimento": "1999-08-21"
        },
        "dataCriacao": "2024-09-20T12:00:00Z"
    }
]
```

### Paginação

Informações de paginação:

`GET http://0.0.0.0:8080/paginacao`

#### Response

```json
{
    "paginaAtual": 1,
    "itensPorPagina": 3,
    "totalDePaginas": 2,
    "totalDeItens": 6,
    "next_page_url": "/api/items?page=2",
    "prev_page_url": null
}
```

