node {
  try {
    stage('Checkout') {
      checkout scm
    }
    stage('Environment') {
      sh 'git --version'
      sh 'docker -v'
      sh 'cp .env_example .env'
      sh 'mkdir -p certs/ certs-data/ logs/nginx/ mysql/ wordpress/'
      sh 'printenv'
    }
    stage('Build') {
        sh 'docker-compose build'
    }
    stage('Deploy'){
        sh 'docker-compose up -d'
    }
  }
  catch (err) {
    throw err
  }
}