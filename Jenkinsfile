pipeline
{
 agent any
 /** tools { 
        maven 'Maven 3.5.0' 
        jdk 'jdk8' 
    }*/
 /**environment
 {
  PATH = "C:/Program Files/apache-maven-3.6.3/bin:$PATH"
 }*/
   stages {
            stage('Repo phase'){
             steps{
               echo 'getting code from repo'
              git "https://github.com/Anushagitacc/sampledeploywebapp.git"
                  }
            }
        /**stage ('Initialize') {
            steps {
                sh '''
                    echo "PATH = ${PATH}"
                    echo "M2_HOME = ${M2_HOME}"
                '''
            }
        }*/
            stage('build phase'){
             
             steps {
              // bat(/"%MAVEN_HOME%\bin\mvn" -Dmaven.test.failure.ignore clean package/)
             bat "mvn clean install"
                //sh 'mvn -Dmaven.test.failure.ignore=true install' 
            }
           // post {
               // success {
                   //junit 'target/surefire-reports/**/*.xml' 
             // }
            //}
            
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
             //  echo 'Deploying the code'
                 sshagent(['deploy_user'])
                 {
                    bat " ssh -o StrictHostKeyChecking=no testcicdapp\0.0.1-SNAPSHOT\testcicdapp-0.0.1-SNAPSHOT.war ec2-user@3.134.76.230:/opt/tomcat/webapp"
                  }
               }
             }
        }
}

