pipeline {
    agent any

    triggers {
        pollSCM('H/5 * * * *') // polls every 5 minutes for changes
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/<your-username>/contact-form.git'
            }
        }

        stage('Build / Test') {
            steps {
                echo "No build required for static HTML"
                // If you had scripts, build/test steps would go here
            }
        }

        stage('Deploy') {
            steps {
                echo "Deployment step will go here"
                // Later you can add Ansible/other deployment commands
            }
        }
    }
}
