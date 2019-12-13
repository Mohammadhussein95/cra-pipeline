pipeline {
  
    agent {
      
        docker {
            image 'node:13.3.0'
            args '-v /root/.m2:/root/.m2:z -u root'
        }
    }
        options {
        skipStagesAfterUnstable()
        }     

    
    stages {
       
      
        stage('Build') {
            
          steps {
               
               sh "curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add - echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list'"
               sh   'sudo apt update && sudo apt install yarn'
               sh  'yarn install'
               sh 'yarn build'


              

       

              
                
  /*             script{
                
                
   /*                  currentBuild.displayName = "qra-${BUILD_NUMBER}${BUILD_ID}"
                    
  } */                                          
            
         
           } 
        }
        
        
/*   stage('Results') {
       
       steps {

             sh " mv ./target/my-app-1.0-SNAPSHOT.jar 'qra-${BUILD_NUMBER}.jar' "
               }
         }

        
        stage('Upload') {
            
            steps {
                script{
                    
                    s3Upload(  entries: [[bucket: 'qra-artifacts/qra-${BUILD_NUMBER}.jar', 
                                        selectedRegion: 'eu-central-1', 
                                        sourceFile: 'qra-${BUILD_NUMBER}.jar' ]], 
                                        profileName: 'jenkins_s3')

                
                }

            } */
        
        
    }
}
