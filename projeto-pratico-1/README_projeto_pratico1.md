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

![PP1-modelo-conceitual](https://github.com/sayuriyoshy/desenvolve-2024/assets/160623866/4fd3ca4a-cbf6-49ba-b6a7-dae1cc401735)

## Modelo Lógico

Todas as entidades identificadas no modelo conceitual se tornaram tabelas, e seus atributos, campos. Além disso, no modelo lógico é possível observa melhor as chaves primárias e estrangeiras, a cardinalidade das relações e a normalização aplicada.

![PP1-modelo-logico](https://github.com/sayuriyoshy/desenvolve-2024/assets/160623866/2cb1373e-59fd-4619-80b6-731f8a780c73)

Arquivo: [PP1_modelo_logico.brM3](https://github.com/sayuriyoshy/desenvolve-2024/blob/630df5c837dd05b90ebcec95774a2e30025d7d40/projeto-pratico-1/PP1_modelo_logico.brM3)

## Modelo Físico

A partir do modelo lógico as informações de tabela e campos foram transferidas para o modelo físico, onde foram definidos os tipos de dados utilizado em cada campo, assim como restrições.

![PP1-modelo-fisico](https://github.com/sayuriyoshy/desenvolve-2024/assets/160623866/d43f65d1-1216-4794-98b6-b1cbabe4eecc)
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
