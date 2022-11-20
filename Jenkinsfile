pipeline{
    agent any
    stages{
        stage('pull the source code'){
            steps{
                echo 'pulling the source code'
                git branch: 'app-deployment-files', url: 'https://github.com/NarsiMyTeaching/weshopify-platform-monolith-app.git'
                echo '==============================='
                echo 'source code pulling completed'
                echo '==============================='
            }
        }
        stage('copying the k8s manifest files to ansible'){
            steps{
                echo 'copying the k8s manifest files'
                sshagent(['Ansible-Machine']){
                    sh 'scp db-manifest-files/*.* ansible-admin@172.31.0.173:/home/ansible-admin/ci-cd-files/k8s-db-files'
                }
            }
        }//CD is completed
        
    }
}
