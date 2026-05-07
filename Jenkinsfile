pipeline {
    environment {
        DOCKERHUB_CREDENTIALS = credentials("dhubb")
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
                sh 'sudo docker login -u ${DOCKERHUB_CREDENTIALS_USR} -p ${DOCKERHUB_CREDENTIALS_PSW}'
                sh 'sudo docker build /home/ubuntu/jenkins/workspace/web/ -t pra5anth/web'
                sh 'sudo docker push pra5anth/web'
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
