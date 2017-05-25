pipeline {
    agent any
    parameters {
        string(name: 'Username', description: 'Openstack Username')
        password(name: 'Password', description: 'Openstack Password')
    }
    environment {
        OS_AUTH_URL = 'https://keystone.arc.ac.za:5000/v3'
        OS_PROJECT_ID=d31af4f236d940c0a2a627c7a8c14595
        OS_PROJECT_NAME="idia-infra-test"
        OS_USER_DOMAIN_NAME="Default"
        OS_USERNAME="{$params.Username}"
        OS_PASSWORD="{$params.Password}"
    }
    stages{
      stage('Transfer'){
       steps {
        sh 'openstack server list'
       }
      }
    }
}
