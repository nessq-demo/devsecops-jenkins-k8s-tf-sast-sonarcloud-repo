pipeline {
  agent any
  tools { 
        maven 'maven_3_5_2'  
    }
   stages{
    stage('CompileandRunSonarAnalysis') {
            steps {	
		sh 'mvn clean verify sonar:sonar -Dsonar.projectKey=qk-sonar-cloud -Dsonar.organization=qk-sonar-cloud -Dsonar.host.url=https://sonarcloud.io -Dsonar.login=1203271ecc669a25d64e0a5f3786a03579c82425'
			}
        } 
  }
}
