pipeline {
    agent any

    stages {
        // Clonar el repositorio desde GitHub
        stage('Clone Repository') {
            steps {
                git branch: 'master', url: 'https://github.com/Drifter624/Pokemon.git'
            }
        }
        
        // Ejecutar pruebas unitarias
        stage('Run Unit Tests') {
            steps {
                script {
                    // Ejecutar pruebas (por ejemplo, con Jest o Mocha en un proyecto Node.js)
                    sh 'npm test'
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
