pipeline {
  agent any
  tools { 
        maven 'maven_3_5_2'  
    }
   stages{
    stage('dependency-check') {
            steps {	
		dependencyCheckPublisher pattern: ''
			}
        } 
  }
}
