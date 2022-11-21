pipeline { 
  agent any
  tools {
    nodejs 'Node v 19.1.0'
  }
  stages { 
    stage('clone repository') {
      steps { 
        git 'https://github.com/Mertangy/gallery'
      }
    }
    
    stage('Build'){
        steps{
            sh 'npm install'
        }
        
    }
    stage('Testing project'){
       steps{
           sh 'npm test'
           }
    }
    stage('Deploying to heroku'){
        steps{  
        withCredentials([usernameColonPassword(credentialsId: 'heroku', variable: 'HEROKU_CREDENTIALS' )]){
        sh 'git push https://${HEROKU_CREDENTIALS}@git.heroku.com/rocky-chamber-48001.git master'

      }
    }     
    }
    }

    post {
      failure{
         emailext body: '$(err)', subject: 'Failed tests', to: 'eric.magesho@student.moringaschool.com'

      }
    }
}
