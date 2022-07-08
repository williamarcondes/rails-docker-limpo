
# Como gerar o projeto Rails

## Tratando erros de permissão de usuário

O Docker cria os arquivos com uma permissão diferente de seu sistema, execute este comando sempre que retornar o erro `permission denied` repetindo novamente o último comando

```
sudo chown -R $USER:$USER .
```
Depois que gerar o banco, o Dockerfile deve criar um grupo para não ocorrer novamente erros assim


## Gerar o projeto
Responda sim, para substituir o  `README.md` e `Gemfile`

```
docker compose run web rails new .
```

Repita o Build do Projeto, para gerar uma imagem com as gemas instaladas
```
docker compose build web
docker compose run web rails webpacker:install
```

## Executando o projeto
```
docker compose up web
```

## Acessando o container
```
docker compose run web bash
```

## Criando o primeiro CRUD
```
rails generate scaffold post title:string content:text
rails db:migrate
```


## Adicionando Gema  action_text

```
rails action_text:install
rails db:migrate
```

## adicionando crud comments
```
rails g resource comment post:references content:text
rails db:migrate
```