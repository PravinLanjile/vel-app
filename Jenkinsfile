pipeline {
     agent {
         label {
             label 'built-in'		 
	         customeWorkspace "/data/pipeline"
		    }
        }
     stages {
         stage ('install-aapache') {
	         steps {
		         sh "yum install httpd -y"
		        }
	        }
	     stage ('deploy-index.html') {
	         steps {
	             sh "cp -r index.html /var/www/html"
		         sh "chmod -R 777 /var/www/html/index.html"
	            }
	        }
	     stage ('Restart-appache') {
	         steps {
		         sh "service httpd restart"
		        }
	        }
        }
    }
