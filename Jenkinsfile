pipeline {
    agent any

    // Esto activa el pipeline cuando GitHub avisa por el túnel
    triggers {
        githubPush()
    }

    // Esto ahora funcionará gracias a lo que configuraste en el Paso B
    tools {
        nodejs 'node18'
    }

    stages {
        stage('Checkout') {
            steps {
                // OJO: Cambia 'master' por 'main' si tu rama principal se llama así
                // Y no olvides poner tu URL real aquí
                git branch: 'main', url: 'https://github.com/DiegoLopez-f/ejercicioCICD'
            }
        }
        stage('Install') {
            steps {
                echo "Instalando dependencias para el proyecto..."
                sh 'node -v'
                sh 'npm -v'
                sh 'npm install'
            }
        }
        stage('Deploy') {
            steps {
                echo "Desplegando aplicación..."
                sh 'echo "Deploy completado exitosamente"'
            }
        }
    }
}