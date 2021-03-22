# Docker

## Build

Para gerar uma imagem a partir do Dockerfile

> Vá para o diretório onde fica o arquivo Dockerfile.

    docker build -t <nome_da_sua_imagem> .

## run

Se a imagem foi gerada sem erro prosiga com os comandos:

> Verifica as imagens que estão disponíveis.

    docker images

> A saída será algo parecido com isso:

    REPOSITORY   TAG       IMAGE ID       CREATED        SIZE
    expresso     1.6.0     06e980a4e060   17 hours ago   1.06GB
    expresso     1.5.0     330c912e6b4c   19 hours ago   1.06GB

Para gerar um container execute o seguinte comando:

Padrão:

    docker run -d -it --name <nome_do_container> <imagem>

Exemplo:

    docker run -d -it --name expresso expresso:1.6.0

## Conatiners

Ver quais containers estão disponíveis e estão no ar.

Comando:

    docker ps

Você vai ver uma lista parecida com essa saída.

    CONTAINER ID   IMAGE            COMMAND                  CREATED        STATUS         PORTS                    NAMES
    2a3713172f45   expresso:1.6.0   "bash -c 'jupyter-la…"   17 hours ago   Up 3 seconds   0.0.0.0:8889->8888/tcp   expresso

Execute o comando para ir para o prompt do container.

Padrão:

    docker exec -it <container_id> /bin/sh

Exemplo:

    docker exec -it 2a3713172f45 /bin/sh

Após esses procedimentos e se der "tudo certo" você assume o prompt do conteiner criado vai aparecer um prompt similar a esse:

    sh-4.4#

## Procedimentos dentro do Container

Depois que assumir o prompt do container você pode testar seu código.

Comandos mais usados:

Acessar o diretório do projeto, os projetos serão salvos no diretório __/opt__:

    sh-4.4# cd /opt/<projeto>

Pare executar os códigos python

    sh-4.4# python3 /diretorio/arquivo.py

ou

    sh-4.4# python3 arquivo.py
