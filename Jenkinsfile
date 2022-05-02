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
      steps { sh 'sonar-scanner \\\n' +
        '  -Dsonar.projectKey=APP-Testing \\\n' +
        '  -Dsonar.sources=. \\\n' +
        '  -Dsonar.host.url=http://localhost:9000 \\\n' +
        '  -Dsonar.login=abe2ad51ccf354b1c96e453d6e3266df1b620d42' }
    }


    stage('Build') {
      steps { sh 'npm run build' }
    }
  }
}
