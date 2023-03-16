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
				        sh "cp /mnt/data-2/index.html /var/lib/docker/volumes/vol2/_data "
				        sh "docker run -itdp 8087:80 -v vol2:usr/local/apache2/htdocs --name server-7 httpd "
					sh "docker exec server-7 chmod -R 777 /usr/local/apache2/htdocs/index.html "
				
		    		}				

		    }

	  }
}
