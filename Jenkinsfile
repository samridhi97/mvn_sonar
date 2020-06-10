pipeline {
   agent any

   stages {
     stage('Git SCM') {
         steps {
            git 'https://github.com/samridhi97/mvn_sonar.git'
         }
      }
stage('Build') {
		steps {
			
				sh '/opt/maven/bin/mvn clean verify '
			
		}
	}
	 
	  
	   stage ('Deploy') {
		steps {
			sh '/opt/maven/bin/mvn clean deploy '
		}
	}
	
   }
}
