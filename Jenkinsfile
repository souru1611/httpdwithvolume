pipeline {
	   agent {
		  label {
			          label "built-in" 
			          customWorkspace "/mnt/data-2" 
		  }	
  	   }

	  stages {

		    stage ("stage-1") {

			   	 steps {	
			          	sh "docker run -d httpd "
			          	sh "docker volume create vol2"
				        sh "docker cp /mnt/data-2/index.html /var/lib/docker/volumes/vol2/_data "
				        sh "docker run -itdp 8082:80 -v vol2:usr/local/apache2/htdocs --name server-2 httpd "
					sh "docker exec server-2 chmod -R 777 /usr/local/apache2/htdocs/index.html "
				
		    		}				

		    }

	  }
}
