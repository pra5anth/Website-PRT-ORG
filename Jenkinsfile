pipeline {
    agent {
        label 'K-M'
    }
    stages {
        stage('Git') {
            steps {
                git url:'https://github.com/pra5anth/Website-PRT-ORG', branch:'main'
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
