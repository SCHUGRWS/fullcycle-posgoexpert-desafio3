# fullcycle-posgoexpert-desafio3

Passos para execução a partir da raiz do projeto

Executar o comando para subir o banco e o rabbitmq 
```shell
docker-compose up
```

Caso não tenha sido feita a migration favor utilizar o comando abaixo
```shell
make migrate
```

Para executar o projeto favor utilizar o comando abaixo
```shell
cd cmd/ordersystem
go run main.go wire_gen.go
```

### Para testar os endpoints Rest utilizar os arquivos na pasta /api
### Para testar o grpc favor utilizar a biblioteca evans
### Para testar o graphql utilizar o playground no endereço http://localhost:8080/
```graphql
query queryOrders {
  orders {
    id
    Price
    Tax
    FinalPrice
  }
}

mutation addOrder {
  createOrder(input: {id: "aaaaa", Price: 10, Tax:10})
  {
    id
    Price
    FinalPrice
    Tax
  }
}
```