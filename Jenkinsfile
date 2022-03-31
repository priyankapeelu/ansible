pipeline {
  agent any

  options {
    ansiColor('xterm')
  }

  environment {
    SSH = credentials('SSH')
  }

  stages {

    stage('Do a Dry Run') {
      steps {
        sh '''
          ansible-playbook roboshop-check.yml -e role_name=frontend -e ansible_user=${SSH_USR} -e ansible_password=${SSH_PSW} -e ENV=sandbox
        '''
      }
    }

  }

}