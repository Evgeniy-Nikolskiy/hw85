pipeline{
    agent{
        label 'ansible'
    }
    stages{
        stage('checkout git'){
            steps{
                git branch: 'main', credentialsId: '375badcc-c089-4993-ae00-f6ecd540ff6e', url: 'git@github.com:Evgeniy-Nikolskiy/hw85.git'
            }
        }
        stage('install dependences'){
            steps{

                sh 'cd roles/elastic_role && pip3 install -r test-requirements.txt'
            }
        }
        stage('run molecule'){
            steps{
                sh 'cd roles/elastic_role && molecule test'
            }
        }
    }
}