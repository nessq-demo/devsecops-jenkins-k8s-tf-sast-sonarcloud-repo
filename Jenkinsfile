pipeline {
  agent any
  tools { 
        maven 'maven_3_5_2'  
    }

   stages{
	stage('SonarQube analysis') {
		steps {
		    
		 //     withSonarQubeEnv('SonarQube') { // If you have configured more than one global server connection, you can specify its name
		      sh 'mvn clean verify sonar:sonar -Dsonar.projectKey=sonar-scan -Dsonar.projectName='sonar-scan' -Dsonar.host.url=http://ec2-3-111-157-158.ap-south-1.compute.amazonaws.com:9000 -Dsonar.token=sqp_b00d47bc0e92c2e345df4f05cc733707a5600e28'
	    }
	 //   }
	  
    stage('dependency-check') {
            steps {	
		dependencyCheck additionalArguments: '--format=HTML', odcInstallation: 'Dependency-Check'
		    archiveArtifacts artifacts: '**/dependency-check-report.html', followSymlinks: false
			}
        } 
  }
}
