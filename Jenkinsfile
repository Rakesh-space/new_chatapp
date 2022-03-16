pipeline {
agent any
 stages {
  stage('Build') {
   steps {
    sh 'rsync -av -e "ssh -o StrictHostKeyChecking=no -i /var/lib/jenkins/myawskey.pem" /var/lib/jenkins/workspace/mypipeline-chattapp/         ubuntu@3.231.230.130:/home/ubuntu/new_chatapp'
   }
 }
 stage('Deploy') {
  steps {
   sh 'ssh -i /var/lib/jenkins/myawskey.pem ubuntu@3.231.230.130 sudo systemctl restart gunicorn'
  }
 }
}
}
