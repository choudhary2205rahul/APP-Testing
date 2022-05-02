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
      steps { sh 'npm run test-headless' }
    }

    stage('Sonar Scan') {
      steps { sh 'npm run sonar-scanner' }
    }

    stage('Snyk Scan') {
      steps { sh 'npm run sonar-scanner' }
    }

    stage('Build') {
      steps { sh 'npm run snyk-scanner' }
    }

  }
}
