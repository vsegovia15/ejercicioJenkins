pipeline {
    agent any
    stages {
        stage('Descargar código') {
            steps {
                checkout scm
            }
        }
        stage('Ejecutar JS') {
            steps {
                sh 'node saludo.js'     // Jenkins en Windows: bat 'node saludo.js'
            }
        }
        stage('Parallel Stage') {
            failFast true
            parallel {
                stage('Branch A') {
                    steps {
                        echo "On Branch A"
                        sleep 5
                        echo "Branch A terminada"
                    }
                }
                stage('Branch B') {
                    steps {
                        echo "On Branch B"
                        sleep 5
                        echo "Branch B terminada"
                    }
                }
            }
        }
    }
}
