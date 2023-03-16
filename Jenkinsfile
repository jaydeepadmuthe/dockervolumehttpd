pipeline {
agent{
label{
		label "built-in"
		customWorkspace "/volume2"
}
}

stages {

		stage ("on master"){
			steps { 
         sh "docker volume create vol2"
	sh "cp /volume2/index.html /var/lib/docker/volumes/vol2/_data/"
        sh "docker run -itdp 804:80 -v vol2:/usr/local/apache2/htdocs --name vq2 httpd"
        sh "docker exec vq2 chmod -R 777 /usr/local/apache2/htdocs/index.html"
      }
    }
}
}
