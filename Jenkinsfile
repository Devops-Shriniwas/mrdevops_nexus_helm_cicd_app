pipeline{
    agent any

    stages{
      stage('sonar quality check'){
          agent{
          docker{
          image 'maven'
          }
          }
          steps{
                script{
                   withSonarQubeEnv(credentialsId: 'sonar-server') {
   

               sh 'mvn clean package sonar:sonar'
           }
    }
    }
    }
    }

}
