def remote=[:]
remote.name = 'ec2'
remote.user = 'ubuntu'
remote.host = 'ec2-47-129-246-98.ap-southeast-1.compute.amazonaws.com'
remote.identityFile = '/var/jenkins_home/.ssh/MSI-SERVER.pem'
remote.allowAnyHosts = true
pipeline {
    agent any
    stages {
        stage('Hello') {
            steps {
                sshCommand(remote: remote, command: "set -x")
                sshCommand(remote: remote, command: "whoami")
                sshCommand(remote: remote, command: "env")
                sshCommand(remote: remote, command: "ls /home/ubuntu/.nvm/versions/node/v20.17.0/bin")
                sshCommand(remote: remote, command: "source ~/.nvm/nvm.sh && node -v")
                sshCommand(remote: remote, command: "source ~/.nvm/nvm.sh && npm -v")
                sshCommand(remote: remote, command: "pwd")
                sshCommand(remote: remote, command: "nvm -v")
                sshCommand(remote: remote, command: "which node")
                sshCommand(remote: remote, command: "set +x")
            }
        }
    }
    post {
        always {
            sleep 5
        }
    }
}
