pipeline {
    agent {
	     node {
             label 'built-in'
	         customWorkspace '/data/wsp-1'
		    }
        }
    stages {
        stage('install-apache') {
            steps {
                sh "yum install httpd -y"
            }
        }
        stage('deploy-index.html') {
            steps {
                sh "cp -r index.html /var/www/html"
                sh "chmod -R 777 /var/www/html/index.html"
            }
        }
        stage('Restart-apache') {
            steps {
                sh "service httpd restart"
            }
        }
    }
}
