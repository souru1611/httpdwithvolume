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
				          sh "docker cp /mnt/data-0 /var/lib/docker/volumes/vol0/_data
				          sh "docker run -itdp 8080:80 -v vol1:/usr/local/apache2/htdocs --name server-0 httpd "
				
				
		    	}				

		    }

	  }
}
