pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Running build automation'
                sh './gradlew build --no-daemon'
                archiveArtifacts artifacts: 'dist/trainSchedule.zip'
            }
        }
        stage('Deploy Staging') {
            steps {
                echo 'Deploying to staging...'
            }
        }
        stage('Sanity Check') {
            input 'Does staging look good?'   
        }
        stage('Deploy Production') {
            steps {
                echo 'Deploying to production...'
            }
        }
    }
}
