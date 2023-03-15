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
        sh "docker run -itp 804:80 -v vol2:/usr/local/apache2/htdocs --name vq2 httpd"
        sh "cp /volume2/pipeline/index.html /var/lib/docker/volumes/index/_data/vol2"
	sh "docker exec vq2 rm -rf /usr/local/apache2/htdocs/index.html"
        sh "docker exec -it chmod 777 /usr/local/apache2/htdocsindex.html"
      }
    }
}
}
