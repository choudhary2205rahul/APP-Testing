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
      steps {
        withMaven(nodejs: 'node') {
          snykSecurity(
            snykInstallation: 'snyk',
            snykTokenId: 'snyk_token_local',
            severity: 'critical',
            failOnIssues: false,
            failOnError: true,
            additionalArguments: '--debug --all-projects --target-reference=' + 'dev'
          )
        }
      }
    }

    stage('Build') {
      steps { sh 'npm run build' }
    }

  }
}
