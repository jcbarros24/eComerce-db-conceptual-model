**Definicoes**
Utilizei as entidades "Cliente", "Produto", "Pedido", "Pagamento", "Endereco" e "Detalhe_pedido" seus atributos e relações para modelar o Banco de Dados.

**Entidades e atributos**
1. A entidade "Cliente" como propriamente diz, terá as definições necessarias de um cliente no nosso Database, utilizando "nome", "sobrenome", "email", "telefone", "cpf" e "id_cliente" como chave primária sendo única para cada instância.
2. A entidade "Endereco" Seria um complemento para a entidade "Cliente" onde teria um endereço mais específico com os atributos: "codigo_postal", "estado", "rua_nome", "rua_complemento", a chave primária "id_endereco" para unicicidade, e a chave estrangeira "id_cliente" para poder relacionar as entidades e apontar um cliente para aquela instância de endereço.
3. A entidade "Pedido" Que funcionaria como o pedido, onde contém seu id_pedido como chave primária para indicar aquele pedido, as chaves estrangeiras "id_cliente" e "id_pagamento" para poder indentificar um pagamento e um cliente relacionados a aquele pedido específico. Também contando com os atributos "data_pedido" e "valor_total" como complementos da entidade.
4. A entidade "Pagamento" com sua chave primária "id_pagamento" garantindo a unicicidade do pagamento, e seus atributos "data_pagamento" e "forma_pagamento"
5. A entidade "Detalhe_pedido" serve como uma entidade para poder complementar as entidades já utilizadas "Pedido" e "Produto", pois possuindo o "id_pedido" e o "id_produto" ele consegue criar uma relação de m:n (citarei abaixo nas relações) entre essas entidades, além de possuir os atributos: "preco_por_item" e "quantidade_produto" para poder fazer o calculo do valor total (que está contido no pedido)

**Relacionamento entre entidades**
1. As entidades "Endereco" e "Cliente" tem uma relação onde Um cliente "possui" um ou mais endereços, e um endereço possui 1 cliente. Essa cardinalidade seria (1:N) Com a explicação da chaves primárias e estrangeiras que citei acima.
2. As entidades "Cliente" e "Pedido" possuem uma relação onde um Cliente "realiza" um ou mais pedidos, mas o pedido se relaciona a apenas um cliente. Seria uma cardinalidade de (N:1) Com a explicação da chaves primárias e estrangeiras que citei acima.
3. As entidades "Pagamento" e "Pedido" possuem uma relação onde em um pedido "efetua" um pagamento, e o mesmo pagamento só possui 1 pedido. Cardinalidade de (1:1) Com a explicação da chaves primárias e estrangeiras que citei acima.
4. As entidades "Pedido" e "Detalhe_pedido" possuem uma relação onde o Detalhe_pedido "complementa" o pedido, um pedido possui vários detalhes, enquanto um detalhe_pedido possui apenas um pedido como referência. Cardinalidade de (1:N) lembrando que como citado acima, a entidade Detalhe_pedido serve como uma entidade para solucionar uma relação (m:n) entre "Pedido" e "Produto"
5. As entidades "Detalhe_pedido" e "Produto" possuem uma relação onde o Detalhe_pedido "inclui" um ou mais produtos, e os produtos podem estar inclusos em mais de um pedido. Cardinalidade de (M:N)
   
