pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                sh 'chmod +x sample_script.sh' // Make sure the script is executable
            }
        }
        stage('Execute Script') {
            steps {
                sh './sample_script.sh' // Execute the script
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
