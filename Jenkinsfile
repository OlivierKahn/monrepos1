pipeline {
    agent any
    tools {
        maven 'Maven353'
        jdk 'java_11'
    }
    stages {
        stage ('Initialize') {
            steps {
                bat '''
                    echo "PATH = %PATH%"
                    echo "M2_HOME = %M2_HOME%"
                '''
            }
        }

        stage ('Build') {
            steps {
                    bat 'cd . & mvn install'
            }
             post {
                success {
                    junit './monappli-domaine/target/surefire-reports/*.xml'
                        }
                 }
            }
        }
}
