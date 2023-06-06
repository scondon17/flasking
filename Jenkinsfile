pipeline {
  agent {
    node {
      label 'docker'
    }

  }
  stages {
    stage('Git') {
      steps {
        git(url: 'https://github.com/scondon17/flasking.git', branch: 'main')
      }
    }

    stage('Docker Build') {
      steps {
        sh 'docker build -t scondon17/flask_app .'
      }
    }

    stage('Docker login') {
      steps {
        sh 'docker login -u scondon17 -p dckr_pat_vN1VrBiUhGBmJR1OJd69MurgXzo'
      }
    }

    stage('Docker Push') {
      steps {
        sh 'docker push scondon17/flask_app'
      }
    }

  }
}