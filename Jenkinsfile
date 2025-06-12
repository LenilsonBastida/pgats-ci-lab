pipeline {
  agent any

  stages {
    stage('Instalar Node.js') {
      steps {
        bat 'npm install nodejs -y --legacy-peer-deps'
      }
    }

    stage('Instalar Yarn') {
      steps {
        bat 'npm install --g yarn'
      }
    }

    stage('Instalar dependências') {
      steps {
        bat 'yarn'
      }
    }

    stage('Instalar Playwright') {
      steps {
        bat 'yarn playwright install'
      }
    }

    stage('Executar testes E2E') {
      steps {
        bat 'yarn run e2e'
      }
    }
  }

  post {
          always {
              archiveArtifacts artifacts: 'playwright-report/**', allowEmptyArchive: true
          }
          failure {
              echo '⚠️ Tests have failed'
          }
          success {
              echo '✅ Tests succeeded'
          }
      }
  } 
