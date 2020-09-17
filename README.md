# hackathon-cloud-devops-2020

# Installation du docker registry

```
docker run -d -p 5000:5000 --restart always --name registry registry:2
```
# Construction de l'image docker
```
docker build -t hackathonDevops .
```
# Envoi de l'image sur le docker registry

```
docker tag nginx localhost:5000/hackathonDevops
docker push localhost:5000/hackathonDevops
```

# Execution du conteneur

```
docker run -p <port>:<port> localhost:5000/hackathonDevops
```

# Installation de Jenkins
1. Installation du docker-compose 

```
sudo curl -L https://github.com/docker/compose/releases/download/1.21.2/docker-compose-$(uname -s)-$(uname -m) -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
docker-compose --version
```
2. Installation de Jenkins
Déplacez-vous à la racine de votre projet et tapez la commande suivante:

```
docker-compose -f Jenkins/docker-compose.yml up -d
```
