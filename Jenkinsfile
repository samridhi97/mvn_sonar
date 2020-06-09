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
			withSonarQubeEnv('sonar') {
				sh '/opt/maven/bin/mvn clean verify sonar:sonar -Dmaven.test.skip=true'
			}
		}
	}
	stage("Quality Gate") {
            steps {
              timeout(time: 1, unit: 'MINUTES') {
                waitForQualityGate abortPipeline: true
              }
            }
          }      
	
   }
}
