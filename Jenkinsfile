#!groovy
// Check ub1 properties
properties([disableConcurrentBuilds()])

pipeline {
    agent { 
        label 'master'
        }
    options {
        buildDiscarder(logRotator(numToKeepStr: '10', artifactNumToKeepStr: '10'))
        timestamps()
    }
    stages {
        stage("Create Docker images") {
            steps {
			sh 'ssh rymar64:Hbvfhdj12345@13.72.67.146 \'sudo rm -rf html2 && sudo git clone https://github.com/rymar24/html2.git\' '
            }
        }
		stage("Build Docker images") {
            steps {
			sh 'ssh rymar64:Hbvfhdj12345@13.72.67.146 \'cd html2 && sudo docker build -t deco . \''
            }
        }
		stage("RUN Docker images") {
            steps {
			sh 'ssh rymar64:Hbvfhdj12345@13.72.67.146 \'sudo docker run -d -p 80:80 deco\''
            }
        }		
    }	
}
