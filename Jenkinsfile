pipeline {
    agent any
    stages {
        stage('Test') {
            steps {
                echo 'Running unit test'
                sh "chmod +x gradlew"
                sh './gradlew clean test --no-daemon'
            }
        }
        stage('Build') {
            steps {
                echo 'Running build'
                sh "chmod +x gradlew"
                sh './gradlew build'
                archiveArtifacts artifacts: 'dist/images.zip'
            }
        }
    }
}
