# Go Movies Crud

Esta é uma API simples para gerenciar um catálogo de filmes. A API permite listar, criar, atualizar e deletar filmes. A aplicação é construída em Go e utiliza o pacote [`mux`](command:_github.copilot.openSymbolFromReferences?%5B%22%22%2C%5B%7B%22uri%22%3A%7B%22scheme%22%3A%22file%22%2C%22authority%22%3A%22%22%2C%22path%22%3A%22%2Fc%3A%2FUsers%2Ffabio%2FDocuments%2Festudos%2Fgo-movies-crud%2Fmain.go%22%2C%22query%22%3A%22%22%2C%22fragment%22%3A%22%22%7D%2C%22pos%22%3A%7B%22line%22%3A34%2C%22character%22%3A11%7D%7D%5D%2C%224ae7a160-fd8e-4029-ad34-003ab4985dbc%22%5D "Go to definition") para roteamento.

## Estrutura do Projeto

```
.gitignore
go.mod
go.sum
main.go
```

## Endpoints

### Listar todos os filmes

**GET** `/movies`

Retorna uma lista de todos os filmes.

### Obter um filme específico

**GET** `/movies/{id}`

Retorna os detalhes de um filme específico com base no ID.

### Criar um novo filme

**POST** `/movies`

Cria um novo filme. O corpo da requisição deve conter os detalhes do filme em formato JSON.

### Atualizar um filme

**PUT** `/movies/{id}`

Atualiza os detalhes de um filme específico com base no ID. O corpo da requisição deve conter os novos detalhes do filme em formato JSON.

### Deletar um filme

**DELETE** `/movies/{id}`

Deleta um filme específico com base no ID.

## Estrutura de Dados

### Filme

```json
{
  "id": "string",
  "isbn": "string",
  "title": "string",
  "director": {
    "firstname": "string",
    "lastname": "string"
  }
}
```

### Diretor

```json
{
  "firstname": "string",
  "lastname": "string"
}
```

## Executando a Aplicação

1. Certifique-se de ter o Go instalado em sua máquina.
2. Clone este repositório.
3. Navegue até o diretório do projeto.
4. Execute o comando [`go run main.go`](command:_github.copilot.openSymbolFromReferences?%5B%22%22%2C%5B%7B%22uri%22%3A%7B%22scheme%22%3A%22file%22%2C%22authority%22%3A%22%22%2C%22path%22%3A%22%2Fc%3A%2FUsers%2Ffabio%2FDocuments%2Festudos%2Fgo-movies-crud%2Fmain.go%22%2C%22query%22%3A%22%22%2C%22fragment%22%3A%22%22%7D%2C%22pos%22%3A%7B%22line%22%3A87%2C%22character%22%3A5%7D%7D%5D%2C%224ae7a160-fd8e-4029-ad34-003ab4985dbc%22%5D "Go to definition") para iniciar o servidor.

A aplicação estará disponível em [`http://localhost:8080`](command:_github.copilot.openSymbolFromReferences?%5B%22%22%2C%5B%7B%22uri%22%3A%7B%22scheme%22%3A%22file%22%2C%22authority%22%3A%22%22%2C%22path%22%3A%22%2Fc%3A%2FUsers%2Ffabio%2FDocuments%2Festudos%2Fgo-movies-crud%2Fmain.go%22%2C%22query%22%3A%22%22%2C%22fragment%22%3A%22%22%7D%2C%22pos%22%3A%7B%22line%22%3A100%2C%22character%22%3A11%7D%7D%5D%2C%224ae7a160-fd8e-4029-ad34-003ab4985dbc%22%5D "Go to definition").

## Exemplo de Uso

### Criar um novo filme

```sh
curl -X POST http://localhost:8080/movies -H "Content-Type: application/json" -d '{
  "isbn": "123456",
  "title": "Novo Filme",
  "director": {
    "firstname": "John",
    "lastname": "Doe"
  }
}'
```

### Listar todos os filmes

```sh
curl http://localhost:8080/movies
```

### Obter um filme específico

```sh
curl http://localhost:8080/movies/1
```

### Atualizar um filme

```sh
curl -X PUT http://localhost:8080/movies/1 -H "Content-Type: application/json" -d '{
  "isbn": "654321",
  "title": "Filme Atualizado",
  "director": {
    "firstname": "Jane",
    "lastname": "Doe"
  }
}'
```

### Deletar um filme

```sh
curl -X DELETE http://localhost:8080/movies/1
```

## Contribuição

Sinta-se à vontade para contribuir com este projeto. Você pode abrir issues e pull requests para melhorias e correções.

## Licença

Este projeto está licenciado sob a licença MIT. Veja o arquivo LICENSE para mais detalhes.

---

Feito com ❤️ por [Seu Nome]
