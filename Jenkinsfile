pipeline {
  agent any
  parameters {
  	string(name:'MAVEN_SETTINGS_XML',defaultValue: 'C://Users//shekshukla//.m2//settings.xml')
  	
  }
  environment {
        ANYPOINT_CRED = credentials('ANYPOINT_CREDENTIALSS') 
      }
  stages {
    stage('Project Build') {
      steps {
        bat "mvn -s ${params.MAVEN_SETTINGS_XML} clean install"
      }
    }
    
    stage('Deploy CloudHub') {
     
      steps {
      
      echo "*************CloudHub Deployment start**************"
        bat "mvn deploy -Dmule.version=4.3.0 -Dusername=shekshukla -Dpassword=Kansas@12345 -Denv=Test -Dappname=jenkinsdemo400 -Dworkers=1 -DworkerType=Micro -DmuleDeploy -DskipTests"
      }
      
    }
    
  }
}