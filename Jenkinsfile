pipeline {
    agent any

    stages {
        // Etapa para clonar el repositorio desde GitHub
        stage('Clone Repository') {
            steps {
                git branch: 'master', url: 'https://github.com/Drifter624/Pokemon.git'
            }
        }
        
        // Etapa para ejecutar un comando básico
        stage('Run Commands') {
            steps {
                script {
                    // Aquí puedes ejecutar cualquier comando, como 'ls' para listar archivos del directorio
                    sh 'echo "Running basic commands..."'
                    sh 'ls -la' // Listar todos los archivos y directorios
                }
            }
        }
    }

    post {
        always {
            echo 'Pipeline completed.'
            cleanWs() // Limpia el workspace después de la ejecución
        }
    }
}
