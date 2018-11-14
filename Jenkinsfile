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
		sh 'mvn -Dhttps.proxyHost=192.168.56.101 -Dhttps.proxyPort=3128 -B -DskipTests clean package' 
            }
        }
	stage('Test') {
            steps {
                sh 'mvn test'
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
    }
}
