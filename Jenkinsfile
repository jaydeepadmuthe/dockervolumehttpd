pipeline {
agent{
label{
		label "built-in"
		customWorkspace "/volume"
}
}

stages {

		stage ("on master"){
			steps { 
        sh "docker volume create vol1"
	sh "cp /volume/index.html /var/lib/docker/volumes/vol1/_data/"
        sh "docker run -itdp 803:80 -v vol1:/usr/local/apache2/htdocs --name vq1 httpd"
        sh "docker exec -it vq1 chmod -R 777 /usr/local/apache2/htdocs/index.html"
      }
    }
}
}
