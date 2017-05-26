pipeline {
    agent any
    def userInput = input(
      id: 'userInput', message: 'Let\'s promote?', parameters: [
      [$class: 'TextParameterDefinition', description: 'Username', name: 'username'],
      [$class: 'PasswordParameterDefinition', description: 'Password', name: 'password']
    ])
    environment {
        OS_AUTH_URL = 'https://keystone.arc.ac.za:5000/v3'
        OS_PROJECT_ID = 'd31af4f236d940c0a2a627c7a8c14595'
        OS_PROJECT_NAME = "idia-infra-test"
        OS_USER_DOMAIN_NAME = "Default"
        OS_USERNAME="{$userInput.username}"
        OS_PASSWORD="{$userInput.password}"
    }
    stages{
      stage('Transfer'){
       steps {
        sh 'workon openstack && openstack server list'
       }
      }
    }
}
