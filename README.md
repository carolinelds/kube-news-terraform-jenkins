# Projeto Kube-news

### Sobre o projeto
O projeto é um simples blog e tem como objetivo ser um exemplo para a criação de cluster Kubernetes na nuvem utilizando Terraform.

### Instruções para subir no DigitalOcean

Requisitos: 
- Terraform instalado
- kubectl instalado
- uma conta no DigitalOcean com API token configurado e chave SSH para acesso à droplets configurada

Na pasta /terraform, criar um arquivo terraform.tfvars e preencher:

```
do_token     = ""
ssh_key_name = ""
region       = ""
```

Executar os seguintes comandos:

```
cd terraform
terraform init
terraform apply >> yes
```

Após, é possível verificar no DigitalOcean a infraestrutura criada.

Para se conectar aos nodes do cluster:

```
cp ./kube_config.yaml ~/.kube/config
kubectl get nodes
```

Para derrubar a infraestrutura criada:

```
terraform destroy >> yes
```