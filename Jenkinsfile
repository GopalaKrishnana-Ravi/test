pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                // Checkout the repository to ensure all files are available
                git 'https://github.com/GopalaKrishnana-Ravi/test.git'
            }
        }
        stage('Build') {
            steps {
                // Ensure the script is executable
                sh 'chmod +x sample_script.sh'
            }
        }
        stage('Execute Script') {
            steps {
                // Execute the script
                sh './sample_script.sh'
            }
        }
    }
    
    post {
        always {
            catchError(buildResult: 'SUCCESS', stageResult: 'FAILURE') {
                mail to: "krishravi2209@gmial.com",
                     subject: "Notification mail from Jenkins",
                     body: "CI/CD pipeline completed successfully.\n\nCheck the application"
            }
        }
    }
}
