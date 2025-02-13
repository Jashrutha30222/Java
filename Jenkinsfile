pipeline {
    agent any  // Runs on any available Jenkins agent

    stages {
        stage('Checkout Code') {
            steps {
                git 'https://github.com/Jashrutha30222/Jenkins1.git'  // Your GitHub repo
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean compile'  // Compiles the project
            }
        }

        stage('Run Tests') {
            steps {
                sh 'mvn test'  // Runs JUnit tests
            }
        }

        stage('Publish Test Results') {
            steps {
                junit '**/target/surefire-reports/*.xml'  // Collects JUnit test results
            }
        }
    }

    post {
        always {
            echo 'Pipeline execution completed.'
        }
    }
}
