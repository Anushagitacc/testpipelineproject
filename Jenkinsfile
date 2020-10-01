def mvnHome
pipeline
{
 agent any
   stages {
            stage('Repo phase'){
             steps{
               echo 'getting code from repo'
              git "https://github.com/Anushagitacc/testpipelineproject.git"
                  }
             }
            stage('build phase'){
            mvnHome = tool 'M3'
               steps{
                    withEnv(["MVN_HOME=$mvnHome"]) {
                       if (isUnix()) {
                                sh '"$MVN_HOME/bin/mvn" -Dmaven.test.failure.ignore clean package'
                                     } 
                                else {
                                  bat(/"%MVN_HOME%\bin\mvn" -Dmaven.test.failure.ignore clean package/)
                                     }
                                                    }
                       }
            }
            stage('Testing Phase'){
            steps
                {
             echo 'testing the code'
                }
            }
            stage('Deploy Phase'){
            steps
                {
               echo 'Deploying the code'
               }
             }
        }
}

