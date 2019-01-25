## Deploy de aplicações NodeJS à AWS com Docker


### Criar projeto, iniciar e adicionar biblioteca express.js

```sh
yarn init -y
yarn add express
```

### Instalação do docker-machine

```sh
base=https://github.com/docker/machine/releases/download/v0.16.0 &&   curl -L $base/docker-machine-$(uname -s)-$(uname -m) >/tmp/docker-machine &&   sudo install /tmp/docker-machine /usr/local/bin/docker-machine
```

### Criar instância EC2 na aws com docker-machine

```sh
docker-machine create --driver amazonec2 aws01
```

### Visualizar variáveis de ambiente do instância recem criada

```sh
docker-machine env aws01
```

### Executa instruções retornadas, no caso será setado variáveis de ambiente

```sh
eval $(docker-machine env aws01)
```


### Criar instância EC2 na aws com docker-machine

```sh
docker-compose -f docker-compose.yml -f docker-production.yml up
```

### Agora basta executar o comando para executar o docker (executar normal como se estivesse rodando local)

```sh
docker-compose -f docker-compose.yml -f docker-production.yml up
```

### Voltar para ambiente docker local

```sh
eval $(docker-machine env -u)
```
