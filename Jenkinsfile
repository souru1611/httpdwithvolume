pipeline {
	   agent {
		  label {
			          label "built-in" 
			          customWorkspace "/mnt/data-1" 
		  }	
  	   }

	  stages {

		    stage ("stage-1") {

			   	 steps {	
			          	sh "docker run -d httpd "
			          	sh "docker volume create vol1"
				        sh "docker cp /mnt/data-1 /var/lib/docker/volumes/vol0/_data "
				        sh "docker run -itdp 8080:80 -v vol1:/usr/local/apache2/htdocs --name server-1 httpd "
					sh "docker exec server-1 chmod -R 777 /usr/local/apache2/htdocs/index.html "
				
		    		}				

		    }

	  }
}
