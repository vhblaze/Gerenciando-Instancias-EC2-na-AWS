#Servidor EC2 com Backup Automático (Data Lifecycle Manager)

Este repositório documenta a configuração de uma instância EC2 utilizada para estudos, bem como a criação de uma política automatizada de snapshots no AWS Data Lifecycle Manager (DLM). O objetivo é demonstrar o gerenciamento básico de uma instância EC2 e a implementação de uma rotina de backup confiável do volume EBS.

1. Descrição do Ambiente

Serviço: Amazon EC2

Sistema Operacional: Amazon Linux 2023

Tipo de instância utilizado: Servidor básico para estudos

Volume EBS:

Tipo: gp3

Tamanho: 8 GiB

IOPS: 3000

Throughput: 125 MB/s

Tag do volume utilizada para aplicar a política:

Name = Servidor basico para estudos

2. Configuração do Backup Automático (Data Lifecycle Manager)

Foi configurada uma política no AWS Data Lifecycle Manager para realizar snapshots automáticos do volume EBS anexado à instância EC2.

Detalhes da Política

Tipo de recurso alvo: Volume

Tag alvo:

Name: Servidor basico para estudos

Descrição da política:

Backup automatico do volume EBS para estudos


Role utilizada:
AWSDataLifecycleManagerDefaultRole

Status: Enabled

3. Agendamento da Política

Nome do agendamento: Schedule 1

Frequência de execução: A cada 12 horas, iniciando às 09:00

Retenção configurada: Manter apenas os 3 snapshots mais recentes

4. Objetivo do Desafio

Este projeto tem como objetivo:

Criar e configurar uma instância EC2 funcional.

Aplicar conhecimentos de EBS, EC2 e DLM na prática.

Configurar políticas de backup automático.

Demonstrar organização, documentação e entendimento dos serviços utilizados.

5. Estrutura Recomendada do Repositório
/
├── README.md
└── images/
      └── (capturas de tela do ambiente)