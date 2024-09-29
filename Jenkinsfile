def remote=[:]
remote.name = 'ec2'
remote.user = 'ubuntu'
remote.host = 'ec2-47-129-246-98.ap-southeast-1.compute.amazonaws.com'
remote.identityFile = '/var/jenkins_home/.ssh/MSI-SERVER.pem'
remote.allowAnyHosts = true
pipeline {
    agent any
    environment {
        VERD_CRED=credentials('')
    }
    stages {
        stage('Hello') {
            script {

            }
            steps {
                sshCommand(remote: remote, command: "whoami")
                sshCommand(remote: remote, command: "env")
                sshCommand(remote: remote, command: "pwd")
                sshCommand(remote: remote, command: "which node")
            }
        }
    }
    post {
        always {
            sleep 5
        }
    }
}
