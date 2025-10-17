pipeline {
    environment {
        DOCKERHUB_CREDENTIALS = credentials("dhub")
    }
    agent {
        label 'K-M'
    }

    stages {
        stage('Git') {
            steps {
                git url:'https://github.com/pra5anth/Website-PRT-ORG', branch:'main'
            }
        }
    stage('Docker') {
            steps {
                sh 'sudo docker login -u pra5anth -p Vinayaga@5'
                sh 'sudo docker build /home/ubuntu/jenkins/workspace/New-tes/ -t pra5anth/pras'
                sh 'sudo docker push pra5anth/pras'
            }
        }
    stage('K8s') {
            steps {
                sh 'kubectl apply -f deploy.yaml'
                sh 'kubectl apply -f service.yaml'
            }
        }
    }
}
