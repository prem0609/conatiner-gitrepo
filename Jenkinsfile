pipeline {
agent{
label{
		label "QA"
		customWorkspace "/mnt/container-1-80"
}
}

stages {

		stage ("slave-ssh"){
			steps {
        sh "rm -rf *"
        sh "sudo yum install docker -y"
        sh "sudo systemctl start docker"
        sh "sudo docker run -itdp 80:80 httpd bash"
      }
    }
}
}
  
  
