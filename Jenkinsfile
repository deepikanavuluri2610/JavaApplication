pipeline {
    agent {
        tools {
            // Specify the Docker installation configured in Jenkins
            // You may need to replace 'Docker' with the actual tool name you configured in Jenkins
            docker 'Docker'
        }
    }

    stages {
    
        stage('Build') {
            steps {
                script {
                    docker.build('my-java-app', '.').run()
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    docker.image('my-java-app').inside {
                        sh 'javac HelloWorld.java'
                        sh 'java HelloWorld'
                    }
                }
            }
        }
    }
}
