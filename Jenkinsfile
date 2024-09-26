pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Build') {
            steps {
                script {
                    // Inicia el contenedor Docker
                    sh 'docker run --name my_container -d -p 80:80 my_image'
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    // Aquí puedes agregar comandos para ejecutar pruebas
                    sh 'echo "Running tests..."'
                }
            }
        }
        stage('Deploy') {
            steps {
                script {
                    // Comandos para desplegar, si es necesario
                    sh 'echo "Deploying..."'
                }
            }
        }
    }
    post {
        always {
            echo 'Cleaning up...'
            sh 'docker stop my_container || true'
            sh 'docker rm my_container || true'
        }
    }
}
