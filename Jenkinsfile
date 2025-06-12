pipeline {
  agent any

  environment {
    NODE_VERSION = 'latest'
  }

  stages {
    stage('Checkout') {
      steps {
        // Clona o repositório
        checkout scm
      }
    }

    stage('Instalar Node.js') {
      steps {
        sh '''
          curl -fsSL https://deb.nodesource.com/setup_${NODE_VERSION}.x | sudo -E bash -
          sudo apt-get install -y nodejs
        '''
      }
    }

    stage('Instalar Yarn') {
      steps {
        sh 'npm install --global yarn'
      }
    }

    stage('Instalar dependências') {
      steps {
        sh 'yarn'
      }
    }

    stage('Instalar Playwright') {
      steps {
        sh 'yarn playwright install'
      }
    }

    stage('Executar testes E2E') {
      steps {
        sh 'yarn run e2e'
      }
    }
  }

  post {
    always {
      echo 'Pipeline finalizado.'
    }
  }
}
