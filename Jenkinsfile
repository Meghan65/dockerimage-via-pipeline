pipeline{
    agent any
    tools{
        jdk "jdk-21"                   //java-name
        dockerTool "docker-25.0.8"     //docker-name
    }

    environment {

        //REGISTRY_URL = "https://index.docker.io/v1/"                     //docker hub url
        IMAGE_NAME   = "shinde1/python-flask-app:via-pipeline"          //push image via pipeline
        CREDS_ID   = "dockerhub-creds"                                  //added docker hub creds 
    }

    stages{

      stage("Docker login"){
       steps{
         script{
            docker.withServer('unix:///var/run/docker.sock'){
            docker.withRegistry('https://index.docker.io/v1/', "${CREDS_ID}"){

              echo "verifying creds"
              
            }
            
            
            }
            
         }
            
       }
     }
      stage("Build docker Image"){
        steps{
          script{
            sh 'docker image build -t $IMAGE_NAME .'
            
            }
          }
               
        }

      }
      stage("Push docker Image into registory"){
        steps{

               sh 'docker image push $IMAGE_NAME'

        }
      }
    }
}
