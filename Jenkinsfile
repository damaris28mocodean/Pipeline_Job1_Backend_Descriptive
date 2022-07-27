pipeline{
  
 agent any
  
    tools {
        maven 'maven3.8.6'
    }
  
    stages {
      
        stage ('Setup parameters'){
          steps{
            script{
              properties([
                        parameters([
                            string(defaultValue: 'pet-rest-api-web-0.0.1-SNAPSHOT', name: 'JAR_FILE_NAME', description: ''),
                            string(defaultValue: '/var/lib/jenkins/workspace/Pipeline_Job2_Backend_Descriptive/Artifacts', name: 'PATH_TO_ARTIFACTS', description: '')
                        ])
                    ])
              
            }
          }
        }
      
        stage ('Initialize') {
            steps {
                sh '''
                    echo "PATH = ${PATH}"
                    echo "MAVEN_HOME = ${MAVEN_HOME}"
                    mvn --version
                '''
            }
        }
      
      stage ('Build with maven'){
        steps{
            sh "mvn --version"
        }
      }
      
      stage ('Store the Artifact'){
        steps{
          sh "echo aici o sa fie ceva!!!"
        }
      }
      
    }
  
}
