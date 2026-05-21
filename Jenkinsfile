pipeline {
    agent any

    stages {
        stage('Build and Test') {
            steps {
                sh 'mvn xdxdxd'
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
    script {
        def logLines = currentBuild.rawBuild.getLog(15).join('\n')

    post {
        always {
            script {
                discordSend(
                    title: "🚀 TEST DISCORD",
                    description: "Jenkins sí está enviando mensajes",
                    footer: "Jenkins",
                    link: env.BUILD_URL,
                    webhookURL: "https://discord.com/api/webhooks/1506351241410904124/UBcD_tniWJRcJu37dtXJ949U38JwJec6iPR-Bv7XqN8ntim5zWxWTmcYtWROs4ViuzqW"
                )
            }
        }
    }
    }
        }
    }
}