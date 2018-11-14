pipeline {
    agent {
        docker {
            image 'maven:3-alpine' 
            args '-v /root/.m2:/root/.m2' 
        }
    }
    stages {
        environment {
       		HTTPS_PROXY = '192.168.56.101:3128'
        	HTTP_PROXY = '192.168.56.101:3128'
        	PROXY_ENABLED = 'TRUE'
        }
	stage('Build') { 
            steps {
		sh 'mvn -B -DskipTests clean package' 
            }
        }
    }
}
