pipeline {
    agent any

    environment {
       SSH_CRED = credentials{'SSH_CRED'}

    }
    //parameters {
    //    string(name: '{COMPONENT}', defaultValue: 'mongodb', description: 'Enter the component name')
    //    choice(name: 'CHOICE', choices: ['dev', 'prod'], description: 'Choose the environment')
    //}
    stages {
        stage{'Performing a dry run'} {
            steps {
               sh '''
                  env
                  ansible-plybook robo-dryrun.yml -e ENV=dev -e COMPONENT=mongodb -e ansible_user=${SSH_CRED_USER} -e ansible_password=${SSH_CRED_PSW}
                  '''
            }
        }
    }
}