pipeline {
  agent any
  tools { 
        maven 'maven_3_5_2'  
    }

   stages{
	stage('SonarQube analysis') {
		steps {
		    def scannerHome = tool 'SonarScanner 4.0';
		    withSonarQubeEnv('SonarQube') { // If you have configured more than one global server connection, you can specify its name
		      sh "${scannerHome}/bin/sonar-scanner"
	    }
	    }
	  }
    stage('dependency-check') {
            steps {	
		dependencyCheck additionalArguments: '--format=HTML', odcInstallation: 'Dependency-Check'
		    archiveArtifacts artifacts: '**/dependency-check-report.html', followSymlinks: false
			}
        } 
  }
}
