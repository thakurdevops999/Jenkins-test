pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo "Repo already checked out by Jenkins."
            }
        }

        stage('Install Dependencies') {
            steps {
                echo "Installing dependencies..."
                // Example: sh 'npm install'  OR  sh 'mvn clean install -DskipTests'
            }
        }

        stage('Run Tests') {
            steps {
                echo "Running tests..."
                // Example: sh 'npm test'  OR  sh 'mvn test'
            }
        }

        stage('Build') {
            steps {
                echo "Building project..."
                // Example: sh 'mvn package'  OR  sh './gradlew build'
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying application..."
                // Example: sh 'scp target/*.jar user@server:/apps/'
            }
        }
    }
}
