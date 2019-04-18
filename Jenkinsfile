node {
                  {
                  stage('SCM Checkout')
                  git credentials: 'git', url: 'https://github.com/Harirao90/test-github' 
                  }
                  
                 stage('Build') {
                 steps {
                     sh 'mvn clean package'
                 }
                 }
                post
                      {
                          success
                               {
                               echo 'Now Archiving ...'
                                       archiveArtifacts artifacts: '**/target/*.war'
                               }
                      }
                          
                  }
                  stage ('Deploy to staging')
                  {
                           steps{
                           build job: 'Deploy to staging'
                           }
                  }


