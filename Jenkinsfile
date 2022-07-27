pipeline{
  
 agent any
  
    tools {
        maven 'maven3.8.6'
    }
  
    stages {
        stage ('Initialize') {
            steps {
                sh '''
                    echo "PATH = ${PATH}"
                '''
            }
        }
    } 
}
