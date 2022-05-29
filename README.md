# Jenkins
## installer jenkins avec docker
### avec docker-compose : 
 version: '2'
 services:
     jenkins:
         image: 'jenkins/jenkins'
         container_name: "jenkins"
         labels:
             kompose.services.type:  nodeport 
         ports:
             -  '8080:8080'
             -  '443:8443'
             -  '50000:50000' 
         volumes: 
             -  /srv/data/jenkins_data:/jenkins_home 
             -  /srv/data/jenkins:/var/jenkins_config

 volumes:
     jenkins_data:
         driver: local
     jenkins_data:
          driver: local   
            
### lancer docker compose
- docker-compose up -d
- verifier jenkins avec le lien 127.0.0.1:8080
- recuper la clé  avec la commande : docker logs jenkins  
## compte jekins: 
 user : oca
 mdp : 21706624KOLda
## creer un job
- cliquer sur new item
- ecrire le nom du job
- choisir le type de job

## configuration users et rôle	 	 
### ajout plugin : Role-based Authorization Strategy
+ permet : 
++ 	roles (groupes d'ensemble de users)
++	users
