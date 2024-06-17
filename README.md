# Stopping containers
`docker container stop $(docker container ls -q)`
Inicie cada conjunto de containers em um terminal diferente de acordo com a necessidade. Para usar as câmeras ou executar a reconstrução de esqueletos, é necessário iniciar os dockers `common` antes e aguardar o processo de inicialização finalizar.

# Requisitos

- [Docker](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-22-04)
- [Docker Compose](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-compose-on-ubuntu-22-04)
- [Nvidia Docker](https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/1.14.3/install-guide.html#installing-with-apt)
- [Nvidia Drivers](https://docs.nvidia.com/datacenter/tesla/tesla-installation-notes/index.html)

# common
`cd cameras`
`docker compose up`
A pasta common possui os containers rabbitmq, zipkin, mjpeg e is-broker-events e é necessário inicializar os dockers desta pasta primeiro.

# cameras
`cd cameras`
`docker compose up`
A pasta cameras inicia os gateways das câmeras.

A pasta cameras possui os arquivos de configuração das câmeras individualmente, cada uma em sua pasta. Caso a quantidade de câmeras não esteja de acordo com o espaço, exclua ou copie as pastas de câmera para a quantidade correta. Atente-se às configurações individuais de cada câmera

# skeletons
`cd skeletons`
`docker compose up`
A pasta skeletons é utilizada para iniciar os containers de processamento de esqueleto e reconstrução 3D
