pipeline{
    agent any
    tools{
        jdk "jdk-21"                   //java-name
        dockerTool "docker-25.0.8"     //docker-name
    }

    environment {

        REGISTRY_URL = "https://index.docker.io/v1/"                     //docker hub url
        IMAGE_NAME   = "shinde1/python-flask-app:via-pipeline"          //push image via pipeline
        CREDS_ID   = "dockerhub-creds"                                  //added docker hub creds 
    }

    stages{

      stage("Docker login"){
       steps{
         script{
           
           docker.withRegistry("${REGISTRY_URL}", "${CREDS_ID}"){
               echo "Verify dockerhub usrename and password"
              
            }
        }
      }
      }
     stage("Build docker Image"){
        steps{

              sh 'docker image build -t $IMAGE_NAME .'
              sh 'docker image ls'
          
            
            }
          }
     stage("Push docker Image into registory"){
        steps{
               echo "$IMAGE_NAME"
               sh 'docker image push $IMAGE_NAME'
               

        }
      }

     }
      
               
        }
         
      
      

