pipeline {
   agent any

   tools {
      go 'go 1.13'
   }

   stages {
      stage('Setup') {
          steps {
              // Get some code from a GitHub repository
            git 'https://github.com/NGKlaure/HelloGo.git'
            
            sh "go get github.com/NGKlaure/HelloGo"
          }
      }
      
      stage('Build') {
         steps {
            // Run Go on a Unix agent.
            sh "go build"
         }

         post {
            success {
               sh "echo BUILD SUCCESS"
            }
         }
      }
      
      stage('Test') {
          steps {
              sh "go test github.com/NGKlaure/HelloGo"
          }
          
          post {
              success {
                  sh "echo SUCCESSFUL TEST"
              }
          }
      }
   }
}
