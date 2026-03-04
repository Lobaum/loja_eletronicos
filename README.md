# Banco de Dados – Loja de Eletrônicos

## Sobre o projeto

Este trabalho tem como objetivo criar e implementar um banco de dados para uma loja de eletrônicos.

A ideia principal foi organizar as informações de clientes, produtos, categorias e pedidos de forma estruturada, utilizando os conceitos de modelagem de dados vistos em aula.

O banco foi desenvolvido em MySQL, utilizando comandos DDL para criação das tabelas e definição dos relacionamentos.


## Estrutura do Banco

O sistema é composto por cinco tabelas principais:

### Cliente

Armazena os dados dos clientes cadastrados na loja.

Campos:

* id_cliente (chave primária)
* nome
* email
* telefone
* data_cadastro


### Categoria

Responsável por organizar os produtos.

Campos:

* id_categoria (chave primária)
* nome
* descricao


### Produto

Guarda as informações dos produtos disponíveis.

Campos:

* id_produto (chave primária)
* nome
* preco
* estoque
* id_categoria (chave estrangeira)

Cada produto pertence a uma categoria.


### Pedido

Registra as compras realizadas pelos clientes.

Campos:

* id_pedido (chave primária)
* data_pedido
* id_cliente (chave estrangeira)
* valor_total

Um cliente pode realizar vários pedidos.


### Item_Pedido

Tabela criada para registrar quais produtos fazem parte de cada pedido.

Campos:

* id_item (chave primária)
* id_pedido (chave estrangeira)
* id_produto (chave estrangeira)
* quantidade
* preco_unitario

Essa tabela foi necessária porque existe um relacionamento muitos-para-muitos entre Pedido e Produto.


## Relacionamentos

* Cliente 1:N Pedido
* Categoria 1:N Produto
* Pedido 1:N Item_Pedido
* Produto 1:N Item_Pedido


## Normalização

O banco foi organizado até a 3ª Forma Normal, evitando:

* Dados repetidos
* Dependências desnecessárias
* Problemas de redundância

A separação das tabelas ajuda a manter os dados organizados e consistentes.


## Como executar

1. Abrir o MySQL.
2. Executar o script SQL fornecido.
3. O banco e as tabelas serão criados automaticamente.


## Considerações finais

O projeto aplica os conceitos de modelagem relacional estudados em sala, utilizando chaves primárias, estrangeiras e organização adequada das tabelas para garantir integridade dos dados.