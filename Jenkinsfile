node {
    checkout scm

    stage('Check NPM Ver') {
        sh 'echo "Hello World"'
    }
    withDockerContainer(args: '-p 3000:3000', image: 'node:16-buster-slim') {
        stage('Build') {
            sh 'npm install'
        }
        stage('Test') {
            sh './jenkins/scripts/test.sh' 
        }
    }
}