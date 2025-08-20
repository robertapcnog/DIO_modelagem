# DIO_modelagem
Construindo um Esquema Conceitual para Banco De dados


# Esquema Conceitual – Oficina Mecânica  

## Descrição do Projeto  
Este projeto tem como objetivo representar um **esquema conceitual** para o gerenciamento de ordens de serviço em uma **oficina mecânica**.  

O sistema permite controlar clientes, veículos, ordens de serviço, equipes de mecânicos, serviços executados e peças utilizadas.  

## Narrativa  
- Clientes levam veículos para revisão ou conserto.  
- Cada veículo é associado a uma equipe de mecânicos.  
- A equipe emite a **Ordem de Serviço (OS)** com previsão de conclusão.  
- O valor da OS é calculado a partir da mão de obra (serviços) e das peças utilizadas.  
- O cliente autoriza a execução e a equipe realiza o trabalho.  

## Entidades e Atributos  
- **Cliente**: idCliente, nome, endereço, telefone  
- **Veículo**: idVeiculo, placa, modelo, ano, idCliente (FK)  
- **OrdemServico**: idOS, data_emissao, data_conclusao, valor_total, status, idVeiculo (FK), idEquipe (FK)  
- **Equipe**: idEquipe, nomeEquipe  
- **Mecânico**: idMecanico, nome, endereco, especialidade, idEquipe (FK)  
- **Serviço**: idServico, descricao, valor_mao_obra  
- **Peça**: idPeca, descricao, valor  
- **OS_Serviço** (associação): idOS, idServico, qtd, valor  
- **OS_Peça** (associação): idOS, idPeca, qtd, valor  

## Relacionamentos  
- Cliente 1 --- N Veículo  
- Veículo 1 --- N OrdemServico  
- Equipe 1 --- N Mecânico  
- Equipe 1 --- N OrdemServico  
- OrdemServico N --- N Serviço (via OS_Serviço)  
- OrdemServico N --- N Peça (via OS_Peça)  

## Diagrama Conceitual  
<img width="822" height="669" alt="image" src="https://github.com/user-attachments/assets/e5d0a4d0-c976-4374-8bbd-d866eb35821d" />


## Observações  
- Algumas informações não estavam na narrativa original (como telefone do cliente ou modelo/ano do veículo), mas foram incluídas para enriquecer o modelo.  
- As tabelas associativas **OS_Serviço** e **OS_Peça** foram criadas porque uma OS pode ter vários serviços e várias peças.  


## Tecnologias e Ferramentas

- Ferramenta de modelagem: [draw.io](https://draw.io)
- Repositório: GitHub



