pipeline {
	agent { label 'ATG'}
     options { 
    skipDefaultCheckout()
    disableConcurrentBuilds()
   }
	   
    stages {
    stage('Clear workspace') {
      steps {
        cleanWs()
      }
    }  
    stage('Source Checkout') {
      steps {
        checkout([$class: 'GitSCM', branches: [[name: '*/master']], 
        doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], 
        userRemoteConfigs: [[credentialsId: 'jvenkat255', url: 'https://github.com/jvenkat255/gradle-pitest-plugin']]])
        }
    }
stage('PITEST') {
    steps {
        bat "gradlew pitest"
    }
} 

             
     
   
    
  }
 
   
} 
