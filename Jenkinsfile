pipeline {
  agent any

  stages {
    stage('Instalar Node.js') {
      steps {
        bat 'npm install nodejs -y'
      }
    }

    stage('Instalar Yarn') {
      steps {
        bat 'npm install --global yarn'
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
}
