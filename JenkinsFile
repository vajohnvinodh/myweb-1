pipeline {
  agent any
  stages {
    stage('Git checkout') {
      steps {
        checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [[$class: 'CheckoutOption']], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'gitaccess', url: 'https://github.com/vajohnvinodh/myweb.git']]])
      }
    }
    stage('Building the image') {
      steps {
        sh """
        docker build -t "javawebapplication" .
        """
      }
    }
  }
}
