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
				        sh "cp /mnt/data-1/index.html /var/lib/docker/volumes/vol1/_data "
				        sh "docker run -itdp 8086:80 -v vol1:/usr/local/apache2/htdocs --name server-6 httpd "
					sh "docker exec server-6 chmod -R 777 /usr/local/apache2/htdocs/index.html "
				
		    		}				

		    }

	  }
}
