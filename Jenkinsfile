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
        steps { sh 'npm install' }
      }

        stage('Build') {
            steps { sh 'npm run test-headless' }
        }
    }
}
