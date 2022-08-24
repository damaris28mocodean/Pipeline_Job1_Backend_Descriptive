pipeline{
  
 agent {
  label 'slaveNode'
  }
  
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
                            string(defaultValue: '/var/lib/jenkins/workspace/Pipeline_Job2_Backend_Declarative/Artifacts', name: 'PATH_TO_ARTIFACTS', description: '')
                        ])
                    ])
              
            }
          }
        }

        stage ('Build with maven'){
          steps{
            dir('source_code'){
              sh "mvn clean install -DskipTests"
            }
          }
        }

        stage ('Store the Artifact'){
          steps{
            dir('source_code/pet-rest-api-web/target'){
              //sh "mv ${JAR_FILE_NAME}.jar ${PATH_TO_ARTIFACTS}/${JAR_FILE_NAME}-${BUILD_NUMBER}.jar"
              sh "jf rt u ${JAR_FILE_NAME}.jar Artifactory --url http://192.168.152.129:8082/artifactory --user admin --password jfrogDamy28&"
            }
          }
        }
      
    }
  
}
