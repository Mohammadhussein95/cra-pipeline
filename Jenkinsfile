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
                sh 'npm install -g grunt-cli'
                sh 'npm install'
                sh 'grunt'
                sh 'npm install -g yarn'
                sh 'npx create-react-app my-app'
                sh 'yarn install'

                sh 'yarn global react-scripts'
                sh 'yarn build'
                
/*               script{
                
                    currentBuild.displayName = "qra-${BUILD_NUMBER}${BUILD_ID}"
                    
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

 
