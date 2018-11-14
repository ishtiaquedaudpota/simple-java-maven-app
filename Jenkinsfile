pipeline {
    agent {
        docker {
            image 'maven:3-alpine' 
            args '-v /root/.m2:/root/.m2' 
        }
    }
    stages {
        stage('Build') { 
            steps {
                withMaven(maven: 'Maven', mavenSettingsConfig: 'c1f0b685-e8b6-4c44-8727-5c4bfe4db803')
		sh 'mvn -B -DskipTests clean package' 
            }
        }
    }
}
