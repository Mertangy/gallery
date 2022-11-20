pipeline { 
  agent any
  stages { 
    stage('clone repository') {
      steps { 
        git 'https://github.com/Mertangy/gallery'
      }
    }
    
    stage('Build'){
        steps{
            sh 'npm install'
            sh 'gulp webpack'
        }
        
    }
    // stage('Testing project'){
    //     steps{
    //         sh 'gradle test'
    //     }
    // }
    stage('Deploying to heroku'){
        steps{
            withCredentials([usernameColonPassword(credentialsId: 'heroku', variable: 'HEROKU_CREDENTIALS' )]){
              sh 'git push https://${HEROKU_CREDENTIALS}@git.heroku.com/rocky-chamber-48001.git master'
              //sh 'git push https://${HEROKU_CREDENTIALS}@git.heroku.com/protected-river-55912.git master'
                
            }
        }
        
    }
    }
}
