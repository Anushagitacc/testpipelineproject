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
            steps
              {
              echo 'Building the code'
             mvn install package
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

