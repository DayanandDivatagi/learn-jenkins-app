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
        stage('With docker file'){
            agent{

                docker{

                    image 'node:18-alpine'
                    reuseNode true
                }

            }
            steps{

                sh '''
                    echo "working in the docker image"
                    ls -la
                    npm install
                    node --version
                    npm --version
                    npm ci
                    npm run build
                   

                '''
            }
        

        }
        stage('Test')
        {
            steps{
                sh'''
                #test -f "/build/index.html" && echo "File exists" || echo "File does not exist"
                npm test
                '''
            }
        }
       
    }
}
