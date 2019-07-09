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
        stage('BuildDockerImage'){
            when {
                branch 'master'
            }
            steps {
                script {
              app = docker.built("kowshik/test")   
                }   }
        }   
}
}
