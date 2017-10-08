pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'chmod +x gradlew'
                sh './gradlew build'
            }
        }
    }
    post {
        success {
            archive 'build/libs/**/*.jar'
        }
        always {
            mail to: 'coskundeniz1989@gmail.com',
                 subject: "Pipeline: ${currentBuild.fullDisplayName}",
                 body: "Something is happen with ${env.BUILD_URL}"
        }
    }
}