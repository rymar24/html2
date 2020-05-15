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
        stage("First step") {
            steps {
                sh 'ssh rymar64:Hbvfhdj12345@13.72.67.146 \'hostname\''
            }
        }
        stage("Second step") {
            steps {
                sh 'ssh rymar64:Hbvfhdj12345@13.72.67.146 \'uptime\''
            }
        }
    }
}
