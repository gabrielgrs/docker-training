# Tutorial Docker

## Procura um container localmente, se não encontrar, baixa ele e executa
sudo docker container run hello-world

## Lista os containers iniciados
sudo docker container ls -a

## Executa um container e remove ele da lista "ps"
sudo docker container run --rm debian

## Executa o container em modo "interativo"
sudo docker container run -it debian bash

## Modo run roda um novo container, ou seja, se criar um arquivo dentro e sair
## ao executar o container novamente, não terá mais o arquivo
sudo docker container run -it debian bash
touch meu-arquivo.txt
ls
exit
sudo docker container run -it debian bash
ls

## Roda container com um nome específico
## Containers precisam ter um nome único/específico
sudo docker container run --name mydeb -it debian bash

## Roda um container já existente
## mydeb: nome do container
sudo docker container start -ai mydeb



## docker run : cria um novo container
## docker start : roda um container existente

## Roda um container com a porta 8080 para acesso externo e a 80 como porta do container
sudo docker container run -p 8080:80 nginx

## Parar um container
sudo docker container stop nome-do-container

## Remover um container
sudo docker container rm nome-do-container

## Remover uma imagem
sudo docker image rm nome-da-imagem

<hr />

# Comandos básicos

## Verifica se possui imagem e inicia ela
sudo docker image run nome_da_imagem

## Baixar imagem do docker Hub
sudo docker image pull nome_da_imagem

## Lista imagens do Docker
sudo docker image ls

## Remover imagem
sudo docker rm nome_da_tag_ou_id

## Inspeciona tag com informações da imagem
sudo docker inspect _nome_imagem_

## Criar uma imagem com tag
sudo docker image nome_da_imagem nome_da_tag

## Constroi imagem a partir de arquivo "descritor"
docker image build

## Publica imagem no registry do docker
docker image push 

# Building Example

## Criando a imagem
sudo docker image build -t ex-simple-build .

## Excuta a imagem criada
sudo docker container run -p 30:80 simple-build

# Salvando imagem no Docker Hub

## Fazendo Login
sudo docker login --username=nome_usuario
sudo docker image push nome_da_imagem:version


<hr />
<hr />

# Tipos de Redes no Docker
sudo docker network ls

sudo docker container run -d --net none nome_imagem
sudo docker container run -d --net host nome_imagem
sudo docker container run -d --net bridge nome_imagem


# Docker Compose

## Iniciando docker-compose em modo daemon
sudo docker-compose up -d

## Parando docker-compose
sudo docker-compose down

## Verificando "composers" que estão rodando
sudo docker-compose ps

