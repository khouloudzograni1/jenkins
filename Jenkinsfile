pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Récupération du code source depuis le référentiel Git
                checkout scm
            }
        }

        stage('Display Date') {
            steps {
                // Affichage de la date système
                script {
                    def date = new Date()
                    echo "Current system date: ${date}"
                }
            }
        }
    }

    triggers {
        // Démarre le build lorsque du code est poussé au référentiel Git
        pollSCM('* * * * *')  // Attention: remplacer par un webhook Git pour éviter des exécutions fréquentes.
    }
}
