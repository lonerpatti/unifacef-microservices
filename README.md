Disciplina: Arquitetura da Informação e Micro serviços.
Prof. CLEBER C. FONSECA
Projeto implementado por Loner Ribeiro Patti.

O projeto foi desenvolvido durante a aula de aula 05/12/2020 do curso de aplicações distribuidas na UNIFacef.


Pré-requisito(s):
- Docker ver. 19.03.
- Visual Studio Code.

#Procedimentos iniciais:#
Baixar a imagem RabbitMQ. Neste caso, faremos o download da imagem com um plugin de gerenciamento para visualizar a interface do servidor RabbitMQ. O comando para baixar ou atualizar uma imagem Docker é "pull"
docker pull rabbitmq:3-management

Iniciar a imagem RabbitMQ Docker:
docker run -d -p 15672:15672 -p 5672:5672 --name rabbit-test-for-medium rabbitmq:3-management

Com o argumento "p", estamos mapeando portas RabbitMQ para portas de contêiner Docker. 15672 é a porta padrão para RabbitMQ GUI, 5672 para RabbitMQ message broker. Com o argumento "name" estamos dando um nome ao nosso container, afim de identificá-lo de uma forma mais legível do que usando o GUID gerado. Isso nos permitirá parar, remover e gerenciar facilmente nossos contêineres. No final, especificamos a imagem do docker a ser executada, neste caso a que extraímos antes.
Se a operação for bem, você verá um GUID como saída.

Teste a imagem abrindo “http://localhost:15672/#/” em seu navegador. O login padrão é guest guest: você deve ver a GUI de gerenciamento do RabbitMQ.

Baixar a imagem RabbitMQ. Neste caso, faremos o download da imagem com um plugin de gerenciamento para visualizar a interface do servidor RabbitMQ. O comando para baixar ou atualizar uma imagem Docker é "pull"
docker pull rabbitmq:3-management

Iniciar a imagem RabbitMQ Docker:
docker run -d -p 15672:15672 -p 5672:5672 --restart=always --name rabbitmq-master rabbitmq:3-management -v "$PWD\docker\rabbitmq\data:/var/lib/rabbitmq"

Com o argumento "p", estamos mapeando portas RabbitMQ para portas de contêiner Docker. 15672 é a porta padrão para RabbitMQ GUI, 5672 para RabbitMQ message broker. Com o argumento "name" estamos dando um nome ao nosso container, afim de identificá-lo de uma forma mais legível do que usando o GUID gerado. Isso nos permitirá parar, remover e gerenciar facilmente nossos contêineres. No final, especificamos a imagem do docker a ser executada, neste caso a que extraímos antes.
Se a operação for bem, você verá um GUID como saída.

6. Teste a imagem em seu navegador abrindo “http://localhost:15672/#/” guest/guest: você deve ver a GUI de gerenciamento do RabbitMQ:
http://localhost:15672/#/