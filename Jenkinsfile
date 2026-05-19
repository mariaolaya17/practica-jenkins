pipeline {
    agent any

    stages {
        stage('Build and Test') {
            steps {
                sh './mvnw comando-falso'
                
            }
        }
    }

    post {
        always {
            junit testResults: 'target/surefire-reports/*.xml', allowEmptyResults: true
        }
    }
}
