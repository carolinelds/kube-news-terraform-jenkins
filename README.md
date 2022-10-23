# Projeto Kube-news

### Sobre o projeto
O projeto é um simples blog e tem como objetivo ser um exemplo para a criação de cluster Kubernetes com containers usando NodeJS e Postgres.

### Observações do projeto
A aplicação é exposta usando a porta 80.

### Instruções para rodar localmente com Kubernetes

Requisitos: Docker, k3d e Kubectl instalados.

Executar os seguintes comandos para rodar o projeto na porta local 80:

```
k3d cluster create <nome-do-cluster> -p "80:30000@loadbalancer"
cd k8s
kubectl apply -f deployment.yaml
kubectl port-forward service/postgre 5432:5432
```

Aguardar a criação dos pods (verificar status com kubectl get pods em outro terminal) e após entrar em localhost:80 no navegador para ver a aplicação.

Para obter informações do cluster, algumas opções:

```
kubectl describe pods
kubectl describe replicaset
kubectl get all
kubectl describe all
```

Removendo o cluster de forma permanente do ambiente local:

```
k3d cluster delete <nome-do-cluster>
```
