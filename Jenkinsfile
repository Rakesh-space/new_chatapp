pipeline {
agent any
 stages {
  stage('Build') {
   steps {
    sh 'rsync -av -e "ssh -o StrictHostKeyChecking=no -i /var/lib/jenkins/myawskey.pem" /var/lib/jenkins/secrets/mypipeline-chattapp/         ubuntu@3.226.242.11:/home/ubuntu/new_chatapp'
   }
 }
 stage('Deploy') {
  steps {
   sh 'ssh -i /var/lib/jenkins/myawskey.pem ubuntu@3.226.242.11 sudo systemctl restart gunicorn'
  }
 }
}
}
