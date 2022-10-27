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
				sh "sudo yum install git -y"
				sh "sudo git init"
        sh "sudo git clone https://github.com/prem0609/container-gitrepo.git"
        sh "sudo yum install docker -y"
        sh "sudo systemctl start docker"
        sh "sudo docker run -itdp 80:80 httpd bash"
      }
    }
}
}
  
  
