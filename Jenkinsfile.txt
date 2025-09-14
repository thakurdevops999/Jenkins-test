pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/<your-username>/sample-jenkins-pipeline.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'pip install -r requirements.txt'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'pytest --maxfail=1 --disable-warnings -q'
            }
        }

        stage('Build') {
            steps {
                echo 'Simulating build...'
                sh 'tar -czf build-artifact.tar.gz src/'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application (simulation)...'
            }
        }
    }

    post {
        always {
            junit '**/test-results.xml' // if you configure pytest to export XML
            archiveArtifacts artifacts: 'build-artifact.tar.gz', fingerprint: true
        }
    }
}
