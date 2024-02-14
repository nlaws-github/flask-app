pipeline {
  agent {
    node {
      label 'docker'
    }

  }
  stages {
    stage('Git') {
      steps {
        git(url: 'https://github.com/nlaws-github/flask-app.git', branch: 'main')
      }
    }

    stage('Build') {
      steps {
        sh 'docker build -t nlawsdocker/jenkins_example .'
      }
    }

    stage('Docker Login') {
      steps {
        sh 'docker login  -u nlawsdocker -p dckr_pat_Ev6ofj0mmOtdivivvAT8a6Pq9qM'
      }
    }

    stage('Push') {
      steps {
        sh 'docker push nlawsdocker/jenkins_example'
      }
    }

  }
}