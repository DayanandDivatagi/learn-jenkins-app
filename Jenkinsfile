pipeline {
    agent any

    stages {
        stage('Without docker image') {
            steps {
                sh '''
                echo "Without docker image"
                touch no_container.txt
                ls -a
                pwd
                '''
            }
        }
       
    }
}
