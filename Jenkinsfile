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
}
}