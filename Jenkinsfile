pipeline {
  agent any

  options {
    ansiColor('xterm')
  }

  environment {
    SSH = credentials('SSH')
  }

  stages {

//    stage('Check Ansible Style Checks') {
//      when { branch pattern: "ROB-.*", comparator: "REGEXP" }
//      steps {
//        echo "Ansible Style Checks"
//        // We will find the right tool.
//      }
//    }
//
//    stage('Run Ansible in Sandbox Environment') {
//      when { branch pattern: "PR-.*", comparator: "REGEXP" }
//      steps {
//        sh '''
//          ansible-playbook roboshop-check.yml -e role_name=frontend -e ansible_user=${SSH_USR} -e ansible_password=${SSH_PSW} -e ENV=sandbox -e CHECK_MODE=true
//        '''
//      }
//    }

    stage('MAIN') {
      when { branch 'main' }
      steps {
        sh '''
          env 
        '''
      }
    }

    stage('TAG') {
      when {
        expression { BRANCH_NAME ==~ ".*" }
      }
      steps {
        sh '''
          env 
        '''
      }
    }

  }

}
