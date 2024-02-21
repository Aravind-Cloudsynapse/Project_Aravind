pipeline{
    agent any
    stages{
        stage("sonar quality check"){
            agent {
                docker {
                    image 'openjdk-8-jdk'
                }
            }
            steps{
                script {
                withSonarQubeEnv(credentialsId: 'sonar-token') {
                     sh 'chmod +x gradlew'
                     sh './gradlew sonarqube'
                 }
                }
             }
        }
    }
}        
