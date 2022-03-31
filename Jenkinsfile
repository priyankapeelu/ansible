pipeline {
  agent any

  options {
    ansiColor('xterm')
  }

  environment {
    SSH = credentials('SSH')
  }

  stages {
// Here we are hardcoding role_name as frontend as for demo purpose, But we need to understand which role has been really modified and we need to parse that
// role name, We can get that infor from git commands, Here is the example.    git diff HEAD@{1} --name-only | grep roles | awk -F / '{print $2}'
    stage('Do a Dry Run') {
      steps {
        sh '''
          ansible-playbook roboshop-check.yml -e role_name=frontend -e ansible_user=${SSH_USR} -e ansible_password=${SSH_PSW} -e ENV=sandbox
        '''
      }
    }

  }

}
