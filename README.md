# fargate
Course on Pluralsight - CloudGuru
Saravanan Dhandapani
[cloudshell-user@ip-10-138-184-206 ~]$ python -V
Python 3.9.16
[cloudshell-user@ip-10-138-184-206 ~]$ node -v
v18.18.2
[cloudshell-user@ip-10-138-184-206 ~]$ npm -v
9.8.1
[cloudshell-user@ip-10-138-184-206 ~]$ docker -v
Docker version 25.0.3, build 4debf41

 npx create-react-app globalmantix

 cd globalmantix
 npm start

Access via port 3000 using Public IP

curl https://icanhazip.com/v4

http://44.221.73.8:3000


==============
Create Dockerfile 

docker build -t globalmantix .

Create ECR 
992382367981.dkr.ecr.us-east-1.amazonaws.com/globamantix

Click "VIEW PUSH COMMANDS"

aws ecr get-login-password --region us-east-1 | docker login --username AWS --password-stdin 992382367981.dkr.ecr.us-east-1.amazonaws.com

docker tag globalmantix:latest 992382367981.dkr.ecr.us-east-1.amazonaws.com/globamantix:latest

docker push 992382367981.dkr.ecr.us-east-1.amazonaws.com/globamantix:latest

====================
Create ECS

Install eksctl in the CLOUD SHELL 
https://eksctl.io/installation/

eksctl create cluster --name globo-eks-cluster --fargate

kubectl create -f deployment.yaml
kubectl create -f service.yaml

# Open svc load_balancer 
http://...

kubectl delete -f deployment.yaml
kubectl delete -f service.yaml

eksctl delete cluster --name globo-eks-cluster