pipeline {
   agent any
   environment{
        BUILD_SERVER_IP='ubuntu@3.110.148.148'
    }
    stages {
   stage('package') {
            steps {
                script{
                sshagent(['QA']) {
                    echo "Packaging the code on new slave"
                   // sh "scp -o StrictHostKeyChecking=no server-config.sh ${BUILD_SERVER_IP}:/home/ubuntu"
                    sh "ssh -o StrictHostKeyChecking=no ${BUILD_SERVER_IP} sudo apt update -y"
                    sh "ssh -o StrictHostKeyChecking=no ${BUILD_SERVER_IP} sudo apt install maven -y"
                }     
            }           
        }
        }
}
}
