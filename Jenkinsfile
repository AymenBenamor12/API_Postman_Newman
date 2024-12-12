pipeline {
    agent any  // Utiliser n'importe quel agent disponible pour exécuter le pipeline

    environment {
        // Définir le chemin de base pour éviter les répétitions
        COLLECTION_PATH = "D:/Doc_personnel/CV/preparation_entretien/test_API/Postman_Booking/Booking_API.postman_collection.json"
        ENVIRONMENT_PATH = "D:/Doc_personnel/CV/preparation_entretien/test_API/Postman_Booking/Booking_API.postman_environment.json"
    }

    stages {
        stage('Run Newman Tests') {
            steps {
                script {
                    echo "Executing Newman API tests..."
                    bat """
                    newman run "${COLLECTION_PATH}" -e "${ENVIRONMENT_PATH}" --reporters cli,htmlextra
                    """
                }
            }
        }

        stage('Deploy Application') {
            steps {
                echo "Deploying the application (placeholder for deployment step)..."
                // Ajoutez ici les étapes de déploiement si nécessaires
            }
        }
    }

    post {
        always {
            echo "Cleaning up the workspace..."
            cleanWs()  // Nettoie les fichiers temporaires dans l'espace de travail Jenkins
        }
    }
}
