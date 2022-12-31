pipeline {
  agent any
    stages {
        stage('Pull') {
             steps{
                script{
                    checkout([$class: 'GitSCM', branches: [[name: '*/main']],
                        userRemoteConfigs: [[
                            credentialsId: 'fdb7bf12-230d-4b33-8613-72b01b079727',
                            url: 'https://github.com/jihed2/angular.git']]])
                }
            }
        }
        }
            }