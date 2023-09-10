pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Check out your GitHub repository
                checkout([$class: 'GitSCM',
                    branches: [[name: '*/main']], // Branch to build
                    userRemoteConfigs: [[
                        url: 'https://github.com/developerarunsingh2/status.git', // GitHub repository URL
                        credentialsId: '1bc7e185-87ad-43f3-8ae4-df9809ecc98c' // Credential ID from Jenkins
                    ]]
                ])
            }
        }

        stage('Build') {
            steps {
                // Build your Java project (e.g., using Maven)
                sh 'mvn clean install'
            }
        }

        stage('Test') {
            steps {
                // Run tests (customize this according to your testing framework)
                sh 'mvn test'
            }
        }

        stage('Deploy') {
            steps {
                // Deploy your Java application (e.g., to a web server)
                // Add deployment commands or scripts here
            }
        }
    }

    post {
        success {
            // This block executes if the pipeline succeeds (all stages pass)
            // You can add notifications or further actions here
        }
        failure {
            // This block executes if the pipeline fails (any stage fails)
            // You can add notifications or cleanup actions here
        }
    }
}
