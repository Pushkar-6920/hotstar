pipeline {

agent any


stages {


stage('Git Checkout'){

steps{

git 'YOUR_GITHUB_REPO'

}

}


stage('Docker Build'){

steps{

sh '''

docker build -t hotstar-frontend ./frontend

docker build -t hotstar-backend ./backend

'''

}

}


stage('SonarQube Analysis'){

steps{

sh '''

sonar-scanner

'''

}

}


stage('Trivy Security Scan'){

steps{

sh '''

trivy image hotstar-frontend

trivy image hotstar-backend

'''

}

}


stage('Docker Push'){

steps{

sh '''

docker login

docker push YOUR_DOCKERHUB/hotstar-frontend

docker push YOUR_DOCKERHUB/hotstar-backend

'''

}

}


stage('Deploy EKS'){

steps{

sh '''

aws eks update-kubeconfig --name hotstar-cluster --region ap-south-1

kubectl apply -f k8s/

'''

}

}


}

}
