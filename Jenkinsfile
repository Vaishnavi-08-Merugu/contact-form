pipeline {
  agent any

  triggers {
    pollSCM('H/2 * * * *')   // example: poll every 2 minutes (customize)
  }

  stages {
    stage('Checkout') {
      steps {
        checkout([$class: 'GitSCM', branches: [[name: '*/main']],
          userRemoteConfigs: [[url: 'https://github.com/Vaishnavi-08-Merugu/contact-form.git']]])
      }
    }

    stage('Run Ansible (WSL)') {
      steps {
        // run ansible-playbook in WSL (Ubuntu)
        bat 'wsl -u vaishu8 -- ansible-playbook -i ansible/inventory ansible/deploy.yml --connection=ssh -v'
      }
    }
  }
}
