pipeline {
    agent any
    
    stages {
        // Clonar el repositorio desde GitHub
        stage('Clone Repository') {
            steps {
                git branch: 'master', url: 'https://github.com/Drifter624/Pokemon.git'
            }
        }
        
        // Construir la imagen Docker con un nombre específico
        stage('Build Docker Image') {
            steps {
                script {
                    // El método 'docker.build' construye la imagen con un nombre específico
                    def customImage = docker.build('pokemon-api-docker')
                }
            }
        }
        
        // Levantar el contenedor con la imagen construida
        stage('Run Docker Container') {
            steps {
                script {
                    // Correr el contenedor basado en la imagen que construiste en la etapa anterior
                    docker.image('pokemon-api-docker').inside {
                        echo 'Docker container is up and running!'
                        // Aquí puedes ejecutar más comandos dentro del contenedor si es necesario
                        // Por ejemplo, correr tests, levantar servicios, etc.
                    }
                }
            }
        }
    }

    // Bloque 'post' para realizar acciones después del pipeline
    post {
        always {
            echo 'Pipeline completed.'
            cleanWs() // Limpia el workspace después de la ejecución
        }
    }
}
