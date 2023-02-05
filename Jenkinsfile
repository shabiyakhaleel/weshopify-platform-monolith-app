pipeline{
    agent any
    
    stages{
        stage('pull the source code'){
            steps{
                echo 'pulling the source code'
                git branch: 'test', url: 'https://github.com/shabiyakhaleel/weshopify-platform-monolith-app.git'
                echo '==============================='
                echo 'source code pulling completed'
                echo '==============================='
            }
        }
    }
}
