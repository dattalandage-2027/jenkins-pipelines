pipeline {
  agent { docker { image 'oven/bun:1.4.4' } }
  options { timestamps(); disableConcurrentBuilds() }
  stages {
    stage('Install') { steps { sh 'bun install --frozen-lockfile' } }
    stage('Typecheck') { steps { sh 'bun run typecheck' } }
    stage('Test') { steps { sh 'bun run test:ci' } }
    stage('Build') { steps { sh 'bun run build' } }
  }
  post { always { archiveArtifacts artifacts: 'coverage/**,dist/**', allowEmptyArchive: true } }
}
