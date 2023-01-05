pipeline {
	agent any
	stages {
		stage('Build') {
			steps {
				bat 'cd . & mvn install'
			}
		post {
                success {
                    junit 'monappli-domaine/target/surefire-reports/*.xml'
                        }
                 }
               
		}
	}
}
