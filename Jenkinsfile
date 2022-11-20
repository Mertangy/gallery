pipeline { 
  agent any
  stages { 
    stage('clone repository') {
      steps { 
        git 'https://github.com/Mertangy/gallery'
      }
    }
    
    // stage('Build project'){
    //     steps{
    //         sh 'gradle build'
    //     }
        
    // }
    // stage('Testing project'){
    //     steps{
    //         sh 'gradle test'
    //     }
    // }
    // stage('Deploying to heroku'){
    //     steps{
    //         withCredentials([usernameColonPassword(credentialsId: 'heroku', variable: 'HEROKU_CREDENTIALS' )]){
    //             sh 'git push https://${HEROKU_CREDENTIALS}@git.heroku.com/protected-river-55912.git master'
                
    //         }
    //     }
        
    // }
    }
}
