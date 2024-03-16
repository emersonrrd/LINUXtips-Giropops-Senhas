apt-get update && apt-get install pip vim -y

docker image build -t emersonrrd/linuxtips-giropops-senhas:1.0 .

docker run -p 6379:6379 --network=host --name giropops-redis -d redis
docker container run --name giropops-senhas -ti -p 5000:5000 --network=host emersonrrd/linuxtips-giropops-senhas:1.0

docker rm giropops-redis -f
docker rm giropops-senhas -f
