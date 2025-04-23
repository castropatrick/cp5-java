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

| Método | Rota                           | Descrição                              | Status Codes       |
| ------ | ------------------------------ | -------------------------------------- | ------------------ |
| GET    | /cards                         | Listar todas as cartas cadastradas     | 200, 500           |
| GET    | /cards/{id}                    | Buscar carta por ID                    | 200, 404, 500      |
| GET    | /decks                         | Listar todos os decks do usuário       | 200, 500           |
| GET    | /decks/{id}                    | Buscar deck por ID                     | 200, 404, 500      |
| GET    | /decks/{id}/cards              | Listar cartas de um deck               | 200, 404, 500      |
| GET    | /decks/{id}/exportar           | Exportar deck em formato JSON ou texto | 200, 404, 500      |
| GET    | /usuarios                      | Listar todos os usuários               | 200, 500           |
| GET    | /usuarios/{id}                 | Obter detalhes de um usuário           | 200, 404, 500      |
| POST   | /cards                         | Cadastrar nova carta                   | 201, 400, 500      |
| POST   | /decks                         | Criar um novo deck                     | 201, 400, 500      |
| POST   | /decks/{id}/cards              | Adicionar carta a um deck              | 201, 400, 404, 500 |
| POST   | /usuarios                      | Criar um novo usuário                  | 201, 400, 500      |
| PUT    | /cards/{id}                    | Atualizar carta existente              | 200, 400, 404, 500 |
| PUT    | /decks/{id}                    | Atualizar deck existente               | 200, 400, 404, 500 |
| PUT    | /decks/{deckId}/cards/{cardId} | Atualizar quantidade ou dados da carta | 200, 400, 404, 500 |
| PUT    | /usuarios/{id}                 | Atualizar dados do usuário             | 200, 400, 404, 500 |
| DELETE | /cards/{id}                    | Excluir carta                          | 204, 404, 500      |
| DELETE | /decks/{id}                    | Excluir deck                           | 204, 404, 500      |
| DELETE | /decks/{deckId}/cards/{cardId} | Remover carta de um deck               | 204, 404, 500      |
| DELETE | /usuarios/{id}                 | Excluir conta de usuário               | 204, 404, 500      |

---


---

## 3. DTOs e Modelos de Dados

### 🔹 DeckDTO
```json
{
  "id": 1,
  "nome": "Rakdos Sacrifice",
  "formato": "Pioneer",
  "descricao": "Deck baseado em sacrifício de criaturas",
  "cartas": [
    {
      "id": 101,
      "nome": "Mayhem Devil",
      "tipo": "Creature",
      "cor": "Red/Black",
      "custoMana": "1BR",
      "quantidade": 4
    }
  ],
  "dataCriacao": "2024-03-15T13:45:00Z"
}
