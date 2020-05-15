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
			sh 'ssh rymar64:Hbvfhdj12345@13.72.67.146 \'pwd\''
                sh 'ssh rymar64:Hbvfhdj12345@13.72.67.146 \'docker build -t deco html2\''
            }
        }
        stage("Run Docker") {
            steps {
                sh 'ssh rymar64:Hbvfhdj12345@13.72.67.146 \'docker run -d -p 80:80 deco\''
            }
        }
    }	
}
