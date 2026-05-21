pipeline {
    agent any

    stages {
        stage('Build and Test') {
            steps {
                sh 'mvn clean verify'
            }
        }
    }

    post {

        always {
            junit testResults: 'target/surefire-reports/*.xml', allowEmptyResults: true
        }

        success {
            discordSend(
                description: "Build exitoso",
                footer: "Jenkins",
                link: env.BUILD_URL,
                result: currentBuild.currentResult,
                title: "Pipeline SUCCESS",
                webhookURL: "https://discord.com/api/webhooks/1506351241410904124/UBcD_tniWJRcJu37dtXJ949U38JwJec6iPR-Bv7XqN8ntim5zWxWTmcYtWROs4ViuzqW"
            )
        }

        failure {
            discordSend(
                description: "Build fallido",
                footer: "Jenkins",
                link: env.BUILD_URL,
                result: currentBuild.currentResult,
                title: "Pipeline FAILED",
                webhookURL: "https://discord.com/api/webhooks/1506351241410904124/UBcD_tniWJRcJu37dtXJ949U38JwJec6iPR-Bv7XqN8ntim5zWxWTmcYtWROs4ViuzqW"
            )
        }
    }
}