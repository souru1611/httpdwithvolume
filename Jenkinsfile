pipeline {
	   agent {
		  label {
			          label "built-in" 
			          customWorkspace "/mnt/data-3" 
		  }	
  	   }

	  stages {

		    stage ("stage-1") {

			   	 steps {	
			          	sh "docker run -d httpd "
			          	sh "docker volume create vol3"
				        sh "docker cp /mnt/data-3 /var/lib/docker/volumes/vol3/_data "
				        sh "docker run -itdp 8083:80 -v vol3:/usr/local/apache2/htdocs --name server-3 httpd "
					sh "docker exec server-3 chmod -R 777 /usr/local/apache2/htdocs/index.html "
				
		    		}				

		    }

	  }
}
