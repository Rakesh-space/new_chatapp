pipeline {
agent any
 stages {
  stage('Build') {
   steps {
     sh 'rsync -v -e "ssh -o StrictHostKeyChecking=no -i /var/lib/jenkins/myawskey.pem" /var/lib/jenkins/workspace/chatappPipeline/ ubuntu@10.0.2.128:/home/ubuntu/new_chatapp'
   }
 }
 stage('Deploy') {
  steps {
    sh 'ssh -i /var/lib/jenkins/myawskey.pem ubuntu@10.0.2.128 sudo systemctl restart gunicorn'
  }
 }
}
}
