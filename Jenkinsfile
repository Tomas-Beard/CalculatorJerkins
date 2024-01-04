pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                // Clone the repository
                git 'https://github.com/Tomas-Beard/CalculatorJerkins.git'
            }
        }

        stage('Build') {
            steps {
                // Build the Java application
                sh 'mvn clean install' // Assuming you are using Maven for the build
            }
        }

        stage('Test') {
            steps {
                // Run unit tests
                sh 'mvn test' // Adjust this command based on your build tool
            }
        }
    }

    post {
        success {
            echo 'Unit tests passed. Ready for deployment!'
        }

        failure {
            echo 'Unit tests failed. Please check your code.'
        }
    }
}
