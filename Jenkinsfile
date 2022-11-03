
  
pipeline {
agent{
label{
		label "QA"
		customWorkspace "/mnt/container-2-85"
     }
     }

stages {

		stage ("slave-ssh"){
			steps { 
			    sh "sudo rm -rf *"
				sh "sudo yum install git -y"
				sh "sudo git init"
				sh "sudo git clone https://github.com/prem0609/container-gitrepo.git"
				sh "sudo gitcheckout 22Q1"
			}
		}
	       stage ("docker-install") {
				steps{	
					sh "sudo yum install docker -y"
				      sh "sudo systemctl start docker" 
			}
               }
	       stage ("cont.85-80") {
		steps { 
		    sh "sudo docker rm -f varun"
		    sh "sudo docker system prune -a -f"
                   sh "sudo docker run -itdp 85:80 --name varun httpd"
                   sh "sudo chmod -R 777 /mnt/container-2-85/container-gitrepo/index.html"
	           sh "sudo docker cp /mnt/container-2-85/container-gitrepo/index.html varun:/usr/local/apache2/htdocs" 
		}
	   }
    }
}
