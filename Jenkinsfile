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
        stage('Install') {
            steps{
                script{
                    sh "sudo npm install"
                }
            }
        }
        stage('Build') {
            steps{
                script{
                    sh "ansible-playbook ansible/build.yml -i ansible/inventory/host.yml"
                }
            }
        }
 stage('Docker') {
            steps{
                script{
                    sh "ansible-playbook ansible/docker.yml -i ansible/inventory/host.yml"
                }
            }
        }
       
        }
        }
            
