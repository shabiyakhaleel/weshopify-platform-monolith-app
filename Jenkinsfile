pipeline{
    agent any
    tools {
        maven "weshopify-platform-maven"
    }
    stages{
        stage('pull the source code'){
            steps{
                echo 'pulling the source code'
                git branch: 'security', url: 'https://github.com/NarsiMyTeaching/weshopify-platform-monolith-app.git'
                echo '==============================='
                echo 'source code pulling completed'
                echo '==============================='
            }
        }
        stage('building the source code'){
            steps{
                echo 'starting the code build'
                sh 'mvn clean deploy -DskipTests=true'
            }
        }

        stage ('download the artifact from jfrog artifactor'){
            steps{
                echo "pushing the artifact to Jfrog Artifactory"
                sh 'jfrog-server-conn.sh'
            }
        }
    }
}
