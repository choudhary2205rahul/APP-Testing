pipeline {

  agent any

    tools {
        nodejs 'node'
    }

    stages {
        stage('Dependencies') {
            steps { sh 'npm install' }
        }

        stage('Test') {
            steps { sh 'npm run test --progress false --watch false' }
        }

        stage('Build') {
            steps { sh 'npm run build' }
        }
    }
}
