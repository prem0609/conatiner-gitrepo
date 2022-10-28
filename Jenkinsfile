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
			}
		}
	       stage ("docker-install") {
				steps{	
					sh "sudo yum install docker -y"
				      sh "sudo systemctl start docker" 
			}
               }
	       stage ("cont.80-80") {
		steps {
        sh "sudo docker run -itdp 80:80 --prem httpd bash"
       sh " sudo chmod -R 777 index.html"
			sh "sudo docker cp index.html prem:/usr/local/apcahe2/htdocs 
		}
	}
    }
}

  
  
