pipeline {
    agent {
        label 'linux'
    }
    stages {
        stage('checkout role'){
            steps{
                dir('mnt-homeworks-ansible') {
                    git branch: 'main', credentialsId: '04dc2180-5b74-4c89-abd4-ef1098b5be10', url: 'https://github.com/FanisIbragimov/mnt-homeworks-ansible.git'
                }
            }
        }
        stage('Install molecule') {
            steps{
                dir('mnt-homeworks-ansible'){
                    sh 'pip3 install -r test-requirements.txt'
                }
                sh "echo =============="
            }
        }
        stage('Run Molecule'){
            steps{
                dir('mnt-homeworks-ansible'){
                    sh 'molecule test'
                }
            }
        }
    }
}
