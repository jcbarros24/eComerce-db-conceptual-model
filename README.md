# Projeto de Banco de Dados - Sistema de E-commerce

Este README documenta as entidades, atributos e relações utilizadas para modelar o banco de dados de um sistema de gestão de vendas online.

## Definições

O modelo consiste nas entidades "Cliente", "Produto", "Pedido", "Pagamento", "Endereço" e "Carrinho", cada uma com seus respectivos atributos e relações.

## Entidades e Atributos

1. **Cliente**: Representa os clientes do e-commerce.
   - Atributos: `id_cliente` (PK), `nome`, `sobrenome`, `email`, `telefone`, `cpf`.

2. **Endereço**: Detalha os endereços de cada cliente.
   - Atributos: `id_endereco` (PK), `codigo_postal`, `estado`, `rua_nome`, `rua_complemento`, `id_cliente` (FK).

3. **Pedido**: Registra as ordens de compra realizadas.
   - Atributos: `id_pedido` (PK), `data_pedido`, `valor_total`, `id_cliente` (FK).

4. **Pagamento**: Gerencia os pagamentos dos pedidos.
   - Atributos: `id_pagamento` (PK), `forma_pagamento`, `data_pagamento`, `pagamento_valido`.

5. **Carrinho**: Lista os produtos selecionados em cada pedido.
   - Atributos: `id_carrinho` (PK), `id_pedido` (FK), `id_produto` (FK), `quantidade_produto`, `preco_por_item`.

6. **Produto**: Cataloga os produtos disponíveis para compra.
   - Atributos: `id_produto` (PK), `nome_produto`, `valor_produto`, `marca_produto`, `tipo_produto`, `quantidade_estoque`.

## Relacionamento entre Entidades

1. **Cliente-Endereço**: Um cliente pode "mora" em vários endereços, mas cada endereço está associado a um único cliente. 
   - Cardinalidade: (1:N)

2. **Cliente-Pedido**: Um cliente pode "realiza" vários pedidos, mas cada pedido está ligado a apenas um cliente.
   - Cardinalidade: (1:N)

3. **Pedido-Pagamento**: Cada pedido "efetua" um pagamento único.
   - Cardinalidade: (1:1)

4. **Pedido-Carrinho**: O "carrinho" "complementa" o pedido, representando os itens específicos escolhidos.
   - Cardinalidade: (1:N)

5. **Carrinho-Produto**: O "carrinho" "inclui" vários produtos, e um produto pode aparecer em vários carrinhos de diferentes pedidos.
   - Cardinalidade: (M:N)

Nota: Este modelo reflete o design conceitual do sistema de banco de dados e será adaptado durante a fase de modelagem lógica para a implementação prática.

