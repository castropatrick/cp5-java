
# CP5-Java
Patrick Castro Quintana - RM559271 1TDSPB
## 📚 Sumário

1. [Introdução](#1-introdução)  
2. [Rotas da API](#2-rotas-da-api)  
3. [DTOs e Modelos de Dados](#3-dtos-e-modelos-de-dados)  
4. [Especificação OpenAPI](#4-especificação-openapi)  
5. [Critérios de Avaliação](#5-critérios-de-avaliação)

---

## 1. Introdução

Esta é a documentação oficial da API RESTful para o sistema de criação e gerenciamento de decks de Magic: The Gathering (MTG). A API permite aos usuários criarem decks, adicionarem cartas, organizarem listas, compartilharem decks e muito mais.

---

## 2. Rotas da API

| Método | Rota                           | Descrição                              | Status Codes       |
| ------ | ------------------------------ | -------------------------------------- | ------------------ |
| GET    | /decks                         | Listar todos os decks do usuário       | 200, 500           |
| GET    | /decks/{id}                    | Buscar deck por ID                     | 200, 404, 500      |
| POST   | /decks                         | Criar um novo deck                     | 201, 400, 500      |
| PUT    | /decks/{id}                    | Atualizar deck existente               | 200, 400, 404, 500 |
| DELETE | /decks/{id}                    | Excluir deck                           | 204, 404, 500      |
| GET    | /decks/{id}/cards              | Listar cartas de um deck               | 200, 404, 500      |
| POST   | /decks/{id}/cards              | Adicionar carta a um deck              | 201, 400, 404, 500 |
| PUT    | /decks/{deckId}/cards/{cardId} | Atualizar quantidade ou dados da carta | 200, 400, 404, 500 |
| DELETE | /decks/{deckId}/cards/{cardId} | Remover carta de um deck               | 204, 404, 500      |
| GET    | /cards                         | Listar todas as cartas cadastradas     | 200, 500           |
| GET    | /cards/{id}
