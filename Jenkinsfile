pipeline {
  agent any

  stages {
    stage('Checkout') {
      steps {
        checkout scm
      }
    }
    stage('Build') {
      steps {
        // Exemplo genérico:
        echo 'Construindo...'
        // Substitua pelo comando real, ex.:
        // bat 'mvn clean package'
      }
    }
    stage('Test') {
      steps {
        echo 'Executando testes...'
        // Ex.: bat 'mvn test'
      }
    }
    stage('Deploy') {
      steps {
        echo 'Publicando artefatos...'
        // Adapte conforme necessidade (deploy, Docker, etc.)
      }
    }
  }
}
