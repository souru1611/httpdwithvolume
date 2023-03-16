pipeline {
	  agent {
		  label {
			          label "built-in" 
			          customWorkspace "/mnt/data-0" 
		  }	
  	}

	  stages {

		    stage ("stage-1") {

			   	 steps {	
			          	sh "docker run -d httpd "
			          	sh "docker volume create vol0"
				        sh "cp /mnt/data-0/index.html /var/lib/docker/volumes/vol0/_data "
				        sh "docker run -itdp 8080:80 -v vol0:/usr/local/apache2/htdocs --name server-0 httpd "
					sh "docker exec server-0 chmod -R 777 /usr/local/apache2/htdocs/index.html "
				
		    		}				

		    }

	  }
}
