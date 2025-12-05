# Servidor EC2 com Backup Automatico Utilizando AWS Data Lifecycle Manager

Este repositório documenta a criação e configuração de uma instância EC2 para fins de estudo, incluindo a implementação de uma política automática de snapshots do volume EBS utilizando o AWS Data Lifecycle Manager (DLM). O objetivo é demonstrar o uso prático dos principais recursos da AWS relacionados à computação em nuvem e gerenciamento de armazenamento.

## 1. Ambiente Utilizado

Servico: Amazon EC2  
Sistema Operacional: Amazon Linux 2023  
Finalidade: Servidor basico para estudos

### Volume EBS
- Tipo: gp3  
- Tamanho: 8 GiB  
- IOPS: 3000  
- Throughput: 125 MB/s  
- Tag aplicada ao volume:

## 2. Politica de Backup Automatico (Data Lifecycle Manager)

Foi configurada uma politica do AWS Data Lifecycle Manager responsavel por criar snapshots automaticos do volume EBS utilizado na instancia EC2.

### Detalhes da Politica

- Tipo de recurso alvo: Volume  
- Filtro por tags:
- Descricao da politica:
- Role utilizada: AWSDataLifecycleManagerDefaultRole  
- Status: Enabled

## 3. Configuracao do Agendamento

- Nome do agendamento: Schedule 1  
- Frequencia: A cada 12 horas  
- Horario inicial: 09:00  
- Retencao: Manter apenas os 3 snapshots mais recentes

## 4. Objetivo do Projeto

Este projeto demonstra:

- A criacao e configuracao de uma instancia EC2 funcional  
- O gerenciamento de volumes EBS  
- A aplicacao de tags para automacao  
- A criacao de politicas de backup com o Data Lifecycle Manager  
- Boas praticas de manutencao e documentacao de ambientes em nuvem

## 5. Estrutura Recomendada do Repositorio
README.md
images/prints

## 6. Como Reproduzir

1. Criar uma instancia EC2 Amazon Linux 2023  
2. Criar ou utilizar um volume EBS e aplicar a tag:
3. Acessar: EC2 → Elastic Block Store → Lifecycle Manager  
4. Criar uma nova politica de snapshot  
5. Configurar:
- Recursos: Volume  
- Filtro: Tag acima  
- Frequencia: 12 horas  
- Retencao: 3 snapshots  
6. Habilitar e salvar a politica
