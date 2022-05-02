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
        withEnv(["CHROME_BIN=/usr/bin/chromium-browser"]) {
          sh 'ng test --progress=false --watch false'
        }
        junit '**/test-results.xml'
      }

        stage('Build') {
            steps { sh 'npm run build' }
        }
    }
}
