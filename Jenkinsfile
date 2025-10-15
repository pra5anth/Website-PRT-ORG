pipeline {
    environment {
        DOCKERHUB_CREDENTIALS = credentials("dhub")
    }
    agent {
        label 'S1'
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
                sh 'sudo docker build /home/ubuntu/jenkins/workspace/t2p/ -t intellipaatpra/prt-task'
                sh 'sudo docker push intellipaatpra/prt-task'
            }
        }
    }
}
