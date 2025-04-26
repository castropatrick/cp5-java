 # CP5-Java 

##  Sumario

1. [Introdução](#1-introdução)  
2. [Rotas da API](#2-rotas-da-api)  
3. [DTOs e Modelos de Dados](#3-dtos-e-modelos-de-dados)  
4. [Especificação OpenAPI](#4-especificação-openapi)  

---

## 1. Introdução

Esta é a documentação oficial da API RESTful para o sistema de criação e gerenciamento de decks de Magic: The Gathering (MTG). A API permite aos usuários criarem decks, adicionarem cartas, organizarem listas, compartilharem decks e muito mais.

---

## 2. Rotas da API


| Método | Rota                     | Descrição                       | Status Codes         |
|--------|--------------------------|---------------------------------|----------------------|
| GET    | /decks                   | Listar todos os decks           | 200, 500             |
| GET    | /decks/{id}              | Buscar deck por ID              | 200, 404, 500        |
| GET    | /users                   | Listar todos os usuários        | 200, 500             |
| GET    | /users/{id}              | Obter dados de um usuário       | 200, 404, 500        |
| GET    | /cards                   | Listar todas as cartas          | 200, 500             |
| GET    | /cards/{id}              | Obter detalhes de uma carta     | 200, 404, 500        |
| GET    | /collections             | Listar coleções de decks        | 200, 500             |
| GET    | /decks/search?query=...  | Buscar decks por nome/descrição| 200, 400, 500        |
| POST   | /decks                   | Criar novo deck                 | 201, 400, 500        |
| POST   | /users                   | Criar novo usuário              | 201, 400, 500        |
| POST   | /cards                   | Adicionar nova carta            | 201, 400, 500        |
| POST   | /collections             | Criar nova coleção              | 201, 400, 500        |
| POST   | /decks/{id}/cards        | Adicionar carta a um deck       | 200, 400, 404, 500   |
| PUT    | /decks/{id}              | Atualizar deck existente        | 200, 400, 404, 500   |
| PUT    | /users/{id}              | Atualizar usuário               | 200, 400, 404, 500   |
| PUT    | /cards/{id}              | Atualizar carta                 | 200, 400, 404, 500   |
| DELETE | /decks/{id}              | Excluir deck existente          | 204, 404, 500        |
| DELETE | /users/{id}              | Deletar usuário                 | 204, 404, 500        |
| DELETE | /cards/{id}              | Excluir uma carta               | 204, 404, 500        |
| DELETE | /decks/{id}/cards/{cardId}| Remover carta de um deck      | 204, 404, 500        |



---

## 3. DTOs e Modelos de Dados

### 🔹 DeckDTO
```json
{
  "id": "PQPz_KSrV0S5_Huk1zh_tg",
  "nome": "Selvala Brostorm",
  "formato": "Commander",
  "descricao": "Deck mono-verde competitivo focado em combos de mana infinita com Selvala, Heart of the Wilds.",
  "cartas": [
    {
      "id": 1,
      "nome": "Selvala, Heart of the Wilds",
      "tipo": "Criatura Lendária",
      "cor": "Verde",
      "custoMana": "1GG",
      "quantidade": 1
    },
    {
      "id": 2,
      "nome": "Phyrexian Dreadnought",
      "tipo": "Artefato Criatura",
      "cor": "Incolor",
      "custoMana": "1",
      "quantidade": 1
    },
    {
      "id": 3,
      "nome": "Umbral Mantle",
      "tipo": "Artefato",
      "cor": "Incolor",
      "custoMana": "3",
      "quantidade": 1
    },
    {
      "id": 4,
      "nome": "Staff of Domination",
      "tipo": "Artefato",
      "cor": "Incolor",
      "custoMana": "3",
      "quantidade": 1
    }
  ],
  "dataCriacao": "2020-06-21T13:45:00Z"
}
```
---
### 🔹 CardDTO
```json
{
  "id": 1,
  "nome": "Selvala, Heart of the Wilds",
  "tipo": "Criatura Lendária",
  "cor": "Verde",
  "custoMana": "1GG",
  "descricao": "Sempre que outra criatura entra no campo de batalha sob seu controle, você pode comprar um card. {T}: Adicione uma quantidade de mana de qualquer combinação de cores igual ao maior poder entre as criaturas que você controla."
}
```

### 🔹 UserDTO
```json
{
  "id": "user_9a8b7c6d",
  "nome": "Patrick Castro",
  "email": "patrick.castro@example.com",
  "dataCriacao": "2020-03-15T10:20:00Z"
}
```
---

## 4. Especificação OpenAPI
A especificação OpenAPI pode ser encontrada em [Especificação OpenAPI](./openapi_full.json).





Link do projeto: https://github.com/castropatrick/cp5-java.git
