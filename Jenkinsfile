pipeline {
    agent any
    parameters  {
    string defaultValue: '', description: 'Name of the GIT TAG to be deployed', name: 'TAG_VALUE', trim: true
    }
        
   
    stages {
        stage("test") {
            steps {
                echo "Tag_name: ${params.TAG_VALUE}"
            }
        }
    
    
    stage('Clone Source') {
      steps {
        dir('adastria-catalog-api') {
          checkout([$class: 'GitSCM', branches: [[name: "${params.TAG_VALUE}"]], 
          doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], 
          userRemoteConfigs: [[credentialsId: 'qbcode_creds', 
          url: 'https://code.qburst.com/adastria/adastria-catalog-mock-api_app.git']]])
        }
      }
    }
    }
    }
