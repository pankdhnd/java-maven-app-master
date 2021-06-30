pipeline {
  agent any
  //declare custom environment variable
  environment{
    NEW_ENV_VAR = "JENKINS_TEST"
  }
    stages{
      stage("build"){
        steps{
          echo "printing from build step"
          echo "Environment varialbe value: ${NEW_ENV_VAR}"
        }
      }
      stage("test"){
          when{
              expression {
                  BRANCH_NAME == 'dev' || BRANCH_NAME =='test' || BRANCH_NAME == 'jenkins-jobs'
              }
          }
        steps{
          echo "printing from test step"
        }
      }
      stage("deploy"){
        steps{
          echo "printing from deploy step"
        }
      }
      stage("cleanup"){
        steps{
          echo "printing from cleanup step"
        }
      }
   }
   post{
       always{
           echo "send email on pipeline completion"
       }
       failure{
           echo "send email on pipeline failure"
       }
       success{
           echo "send email on pipeline success"
       }
       changed{
           echo "it seems build stauts was changed from the last time"
       }
   }
} 
