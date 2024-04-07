pipeline {
  agent { label 'spc' }
  stages {
	stage('git') {
		  steps {
			git url: 'https://github.com/dummyrepos/spring-petclinic-apr24.git', branch: 'main'
		  }
	}
	stage('build') {
	  steps {		
		sh 'mvn clean package'
		junit testResults: '**/surefire-reports/*.xml'
		archive '**/target/spring-petclinic-*.jar'		
	  } 
	}
	
  }
    
}
