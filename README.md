# Projeto Conceitual e Lógico de Banco de Dados - Oficina Mecânica

![Diagrama Lógico - Oficina Mecânica](diagrama-logico-oficina.png)
<!-- Suba a imagem exportada do draw.io e ajuste o nome do arquivo acima -->

## Descrição do Projeto

Este repositório contém o **modelo conceitual** e **lógico** de banco de dados para um sistema de controle e gerenciamento de **Ordens de Serviço (OS)** em uma **oficina mecânica**, desenvolvido como entrega do desafio **"Construindo um Esquema Conceitual do Zero"** da plataforma DIO.

### Narrativa do Negócio (Resumo)

- Clientes levam veículos para consertos ou revisões periódicas.
- Cada veículo é alocado a uma equipe de mecânicos.
- A equipe identifica serviços necessários, preenche a **OS** com data prevista de entrega.
- OS inclui: número, data de emissão, valor total, status e data de conclusão.
- Valor da OS = mão de obra (tabela de referência) + peças utilizadas.
- Cliente autoriza a execução.
- Mecânicos possuem código, nome, endereço e especialidade.
- Relacionamentos N:N: uma OS pode ter vários serviços/peças e vice-versa.

### Objetivos do Desafio

Criar um esquema conceitual do zero a partir da narrativa, identificando:
- Entidades
- Relacionamentos
- Atributos
- Cardinalidades

E converter para o modelo lógico (tabelas relacionais com chaves primárias/estrangeiras).

## Diagrama Entidade-Relacionamento (Conceitual e Lógico)

O diagrama foi modelado no **draw.io (diagrams.net)**.

**Principais entidades e relacionamentos:**

- Cliente → possui → Veículo
- Veículo → gera → Ordem de Serviço
- Ordem de Serviço → contém → Item de Serviço (N:N com Servico)
- Ordem de Serviço → utiliza → Item de Peça (N:N com Peca)
- Mecânico → trabalha em → Ordem de Serviço (N:N)

Arquivos incluídos:
- `oficina-mecanica.drawio` → arquivo editável do draw.io
- `diagrama-logico-oficina.png` → exportação do diagrama lógico

## Modelo Lógico (Tabelas SQL)

O modelo lógico completo foi implementado com as seguintes tabelas principais:

- Cliente
- Veiculo
- Mecanico
- Servico (tabela de referência de mão de obra)
- Peca
- OrdemDeServico (central)
- ItemServico (associativa N:N OS × Servico)
- ItemPeca (associativa N:N OS × Peca)
- OS_Mecanico (associativa N:N OS × Mecanico)
