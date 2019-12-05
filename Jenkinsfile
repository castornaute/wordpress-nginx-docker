node {
  try {
    stage('Checkout') {
      checkout scm
    }
    stage('Environment') {
      sh 'git --version'
      echo "Branch: ${env.BRANCH_NAME}"
      sh 'docker -v'
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