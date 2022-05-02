pipeline {

    agent { label 'standard' }

    tools {
        nodejs 'npm'
    }

    stages {
        stage('Install') {
            steps { sh 'npm install' }
        }

//        stage('Test') {
//
//            steps { sh 'npm run test' }
//
//        }
//
//        stage('Build') {
//            steps { sh 'npm run build' }
//        }
    }
}
