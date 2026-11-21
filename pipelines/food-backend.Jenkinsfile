pipeline {
  agent { docker { image 'oven/bun:1.4.4' } }
  options { timestamps(); disableConcurrentBuilds() }
  stages {
    stage('Install') { steps { sh 'bun install --frozen-lockfile' } }
    stage('Typecheck') { steps { sh 'bun run typecheck' } }
    stage('Test') {
      environment { USE_IN_MEMORY_DB = 'true' }
      steps { sh 'bun run test:ci' }
    }
  }
  post { always { archiveArtifacts artifacts: 'coverage/**', allowEmptyArchive: true } }
}
