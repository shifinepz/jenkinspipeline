pipeline{
	agent any
	stages {
		stage("tomcat installation & auth config"){
			steps {
				sh 'echo "Hello lets start the installation"'
				git 'https://github.com/shifinepz/2018.git'
                
			}
		}
		stage("tomcat starting on port 80") {
			steps {
				sh 'echo "starting tomcat service"'
				sh '''./tomcat.sh
				sudo systemctl start tomcat
				sudo systemctl status tomcat'''
				sh 'echo "Access http://locahost:80 on your web browser"'
			}
		}
		stage("webapp deployment"){
			steps{
				sh '''sudo cp /opt/Devops/java/cacheImplement-2.4-SNAPSHOT.war /var/lib/tomcat/webapps/
				sudo systemctl restart tomcat
				sudo systemctl status tomcat.service'''
			}
			steps {
			input('Access tomcat port 80 and click proceed !')
        	}
		}
		stage("redeploy webapp to port 8080"){
			steps{
				git 'https://github.com/shifinepz/redeploy.git'
				sh './redeploy.sh'
			}
		}
}
}