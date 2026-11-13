pipeline {
    agent any
    environment {

        GIT_BRANCH = 'main'
        REPOSITORY_URL = 'https://github.com/dheerajguttedar/Amazon-Jenkins'
    }
    stages {

        stage('pull scm git ') {
            steps {
               git branch: "${GIT_BRANCH}"
                    url: "${REPOSITORY_URL}"
            }
        }
        stage('compile ') {
            steps {
                sh 'mvn compile'
            }
        }

        stage('build') {
            steps {
                 sh 'mvn clean install'
            }
        }

        
    }

  post{

  success{
     echo 'Build success 1'
  }
    
  failure{
       echo 'Failure in the build'
   }

  }


}
