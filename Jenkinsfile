pipeline {
    agent {
        docker {
            image 'node:16-buster-slim' 
            args '-p 3000:3000'
        }
    }
}

node {
    stage('Checkout') {
        checkout scm
    }
    stage('Check NPM Ver') {
        sh 'npm --version'
    }
    stage('Build') {
        sh 'npm install'
    }
    stage('Test') {
        sh './jenkins/scripts/test.sh' 
    }
}