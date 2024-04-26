# Sobre o 1º Projeto Prático

Esse é um projeto de modelagem de banco de dados relacional para uma loja física de uma marca de perfumaria e produtos de cuidado e beleza (case fictício). 

O projeto levou em consideração conceitos e entidades relacionados a parte de **vendas**, **sistema de pontuação** e **gestão de produtos em estoque,** para criar a modelagem lógica e física do banco de dados, como proposto no desafio.

A implementação desse projeto envolve a transição do modelo conceitual, para o lógico e por fim, o modelo físico, que utiliza linguagem SQL.

*O projeto entregue fez parte da trilha de Dados do Desenvolve 2024, programa gratuito de formação e inclusão em tecnologia do Grupo Boticário.*

## Fluxograma do projeto

1. **Análise dos requisitos:** etapa inicial responsável pelo estudos das exigências do projeto e pela escolha do segmento relacionado ao Boticário que seria adotado para a construção da modelagem. O segmento escolhido foi: loja física.
1. **Modelo Conceitual:** utilizado o Diagrama de Entidade Relacionamento para ilustrar e descrever as entidades, relacionamentos e atributos, referentes ao negócio levantadas na etapa anterior.
2. **Modelo Lógico:** baseado no modelo conceitual, esquematiza as entidade, relacionamento e atributos, em forma de tabelas e colunas, além de identificar as chaves primárias e estrangeiras. 
3. **Modelo Físico:** a evolução dos modelos anteriores para a linguagem próxima da implementação. Aqui, o tipo de atributos e suas restrições são identificadas.

## Modelo Conceitual

Para criar o modelo foi escolhido o segmento loja física e identificada as possíveis entidades, relacionamentos e atributos, ligados a esse recorte. Criei a seguinte situação para começar o meu diagrama:

A nova loja física da marca e franqueadora **Beleza Viva**, inaugurada em Goiânia, precisa da um banco de dados que comporte informações essenciais para o negócio como: dados sobre os clientes, vendas, programa de pontuação, além de produto para que seja possível a gestão efetiva do estoque.

A partir desse cenário fictício foi criado o Diagrama Entidade Relacionamento abaixo, onde classifico as entidades fortes como: Clientes e Centro de Distribuição; e as demais como entidades fracas. 

![PP1-modelo-conceitual](https://github.com/sayuriyoshy/desenvolve-2024/assets/160623866/0630f703-a6db-47df-a85e-ebd766a191fe)

## Modelo Lógico

Todas as entidades identificadas no modelo conceitual se tornaram tabelas e seus atributos em campos. Além disso, no modelo lógico é possível observar melhor as chaves primárias e estrangeiras, a cardinalidade das relações e a normalização aplicada.

![PP1-modelo-logico](https://github.com/sayuriyoshy/desenvolve-2024/assets/160623866/5049e30f-02eb-40b5-a537-0666e8d8de5f)

Arquivo: [PP1_modelo_logico.brM3](https://github.com/sayuriyoshy/desenvolve-2024/blob/630df5c837dd05b90ebcec95774a2e30025d7d40/projeto-pratico-1/PP1_modelo_logico.brM3)

### Detalhes sobre tabelas e campos


**Cliente:** entidade forte que armazena informações sobre os clientes da loja. A entidade se relaciona com a entidade “Compra” e “Programa Pontuação” que são importantes para adquirir informações a respeito de vendas e programa de pontuação.

**Chave primária:** cod_cliente

**Atributos:** 
- nome → nome e sobrenome do cliente
- cpf → CPF do cliente
- telefone → número celular ou residencial com DDD e sem caracteres especiais
- data_de_nascimento → data de nascimento no formato DD/MM/AAAA
- email → endereço de email para cadastro e contato, envio de publicidade e comunicados.
- endereço → informação de endereço completa com **rua**, **bairro**, **cidade,** **estado e CEP**.

**Centro de Distribuição (CD):** entidade forte que se relaciona diretamente com “Produtos” e armazena informações sobre o CD que é responsável pelo abastecimento do estoque da loja.

**Chave primária:** cod_cd

**Atributos:**
- nome_cd: nome do centro de distribuição responsável pelo abastecimento da loja física.
- cod_sku: código identificador único de 5 números fornecido a cada produto.
- qtd_produtos: quantidade disponível do produto no CD.


**Compra:** entidade fraca relacionada a “Cliente” e “Programa Pontuação”, que armazena e fornece dados sobre as vendas realizadas na loja física.

**Chave parcial e chave estrangeira:** cod_compra e cod_cliente.

**Atributos:**
- valor_compra → valor total da venda pago pelo cliente após os descontos atribuídos.
- valor_desconto → valor total do desconto atribuído a venda.
- valor_produtos → valor total bruto da venda sem descontos atribuídos
- data_compra → data completa da compra incluindo horário em formato DD/MM/AAAA HH:MM:SS


**Item_compra:** entidade relacional ligada a “Compra” e “Produtos” que fornece detalhes sobre os itens vendidos a partir de determinada compra.
**Chave parcial e chave estrangeira:** cod_compra e cod_sku.
**Atributos:**
- preco_final → valor líquido do produto após descontos
- desconto → valor do desconto em reais (R$)
- preco_item → valor bruto do produto
- qtd_produtos → quantidade vendida sob o produto


**Programa Pontuação:** entidade fraca relacionada a “Compra” que armazena informações sobre a pontuação atribuída ou resgatada em cada compras realizada na loja física. É preciso estabelecer e aplicar a lógica de pontos a partir das regras para o programa.

**Chave parcial e estrangeira:** cod_compra e cod_cliente

**Atributos:**
- pontuacao → histórico de pontos realizados pela pessoa cliente.
- pontuacao_disponivel → quantidade de pontos disponíveis para resgate pela pessoa cliente
- entrada_pontos → quantia de pontos atribuídos a partir de uma compra
- Data_entrada → data completa da entrada de pontos no formato DD/MM/AAAA HH:MM:SS
- saída_pontos → quantia de pontos resgatadas a partir de uma compra
- data_saida → data completa da saída de pontos no formato DD/MM/AAAA HH:MM:SS
- vencimento → data limite para resgate da pontuação disponível antes do reset


**Produtos:** entidade fraca ligada a “C_Distribuição” e “Estoque_Loja”. Armazena informações detalhadas sobre os produtos disponíveis e vendido a partir da loja.

**Chave parcial e estrangeira:** cod_sku e cod_cd

**Atributos:**
- nome_produto: nome completo do produto
- categoria → categoria em que o produto está. Exemplo: Perfumaria, corpo e banho etc.
- subcategoria → subcategoria derivada da categoria. Exemplo: Desodorante, sabonete, hidratante etc.
- marca → nome marca da linha do produto. Exemplo: La Belle (marca de perfume), Make Viva (linha de maquiagem) etc.
- preco → valor bruto real do produto sem descontos atribuídos.

**Estoque_loja:** entidade fraca que recebe dados de “C_Distribuição” e “Produtos”, e retorna informações importante para a gestão do estoque físico local. 

**Chaves parcial e estrangeira:** cod_sku e cod_cd

**Atributos:**
- qtd_estoque → quantidade disponível do produto no estoque local.


## Modelo Físico

A partir do modelo lógico as informações de tabela e campos foram transferidas para o modelo físico, onde foram definidos os tipos de dados utilizado em cada campo, assim como restrições.

![PP1-modelo-fisico](https://github.com/sayuriyoshy/desenvolve-2024/assets/160623866/9445151d-eeb1-403e-b133-a7e6bd5edd25)

Arquivo: [PP1_modelo_fisico.architect](https://github.com/sayuriyoshy/desenvolve-2024/blob/630df5c837dd05b90ebcec95774a2e30025d7d40/projeto-pratico-1/PP1_modelo_fisico.architect)

## Ferramentas utilizadas

- BrModelo
- SQL Power Architect

## Como utilizar o projeto?

Como exemplo para projetos similares de banco de dados para lojas físicas.

## Contribuições

Contribuições e sugestões são muito bem-vindas! Sinta-se à vontade para sugerir evoluções ou correções e assim contribuir também com o meu desenvolvimento.

### Autora
Sayuri Yoshy

[![LinkedIn](https://img.shields.io/badge/linkedin-%230077B5.svg?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/sayuri-yoshy/)
