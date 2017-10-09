pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building'
                sh 'chmod +x gradlew'
                sh './gradlew build'
            }
        }
        input 'Do you approve deployment?
        stage('Deploy - Prod') {
            steps {
                echo 'Deployinggg'
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
