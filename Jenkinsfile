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
                   withSonarQubeEnv(credentialsId: 'sonar-tokenn') {
   

               sh 'mvn clean package sonar:sonar'
           }
    }
    }
    }
        
        
         stage('Quality Gate Status'){

        steps{

            script{
                waitForQualityGate abortPipeline: false,  credentialId:'sonar-toknn'
                                              
                                              
                                            
            }

        }
    }
    }

}
