pipeline {
  agent any
  tools { 
        maven 'maven_3_5_2'  
    }
   stages{
    stage('dependency-check') {
            steps {	
		dependencyCheck additionalArguments: '--format=HTML', odcInstallation: 'Dependency-Check'
		    archiveArtifacts artifacts: '**/*.html', followSymlinks: false
			}
        } 
  }
}
