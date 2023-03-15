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
        sh "docker run -itdp 803:80 -v vol1:/usr/local/apache2/htdocs --name vq1 httpd"
        sh "cp /volume/pipeline/index.html /var/lib/docker/volumes/index/_data/vol1"
        sh "docker exec -it chmod 777 /usr/local/apache2/htdocsindex.html"
      }
    }
}
}
