# Portal Notícias - Deploy com Kubernetes
Este repositório contém os arquivos necessários para a configuração e deploy do sistema Portal Notícias utilizando Kubernetes e Docker Desktop.

## 🎯 Pré-requisitos
Certifique-se de ter o seguinte configurado antes de prosseguir:

- Docker Desktop instalado e em execução
- Configuração do kubectl (Ferramenta de linha de comandos para interagir com o Kubernetes)

## ⚙️ Configurações e Implantação
Siga os passos abaixo para implantar o sistema no Kubernetes:

1. Configure o contexto no Kubernetes:
Use o comando abaixo para garantir que o contexto do Kubernetes seja direcionado ao Docker Desktop:


kubectl config use-context docker-desktop
2. Aplique os arquivos de configuração:
Execute os comandos abaixo para criar e configurar os recursos no cluster Kubernetes:

kubectl apply -f portal-noticias.yaml
kubectl apply -f svc-portal-noticias.yaml
kubectl apply -f db-noticias.yaml
kubectl apply -f svc-db-noticias.yaml
kubectl apply -f db-configmap.yaml
kubectl apply -f sistema-configmap.yaml
kubectl apply -f portal-configmap.yaml

3. Verifique no terminal os endpoints disponíveis:
Após aplicar os recursos, os serviços estarão disponíveis nas seguintes URLs:

Porta: localhost:30000
Porta: localhost:30001

## 🛠️ Ferramentas Utilizadas
Docker Desktop para criar e gerenciar os contêineres.
Kubernetes & kubectl para orquestração dos serviços e gerenciamento do cluster.


## 📢 Notas Adicionais
Realize um monitoramento contínuo do estado dos pods, serviços e outros recursos usando o comando:
bash

kubectl get all
Certifique-se de que as portas 30000 e 30001 estejam livres no sistema para evitar conflitos.