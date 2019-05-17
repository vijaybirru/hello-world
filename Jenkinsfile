node{
	stage('Checkout'){
		//Checkout the code from a GitHub repository
		git 'https://github.com/vijaybirru/hello-world.git'
	}
	stage('build'){
		sh '"/opt/maven/bin/mvn" -V clean compile'
	}
               stage('test'){
		sh '"/opt/maven/bin/mvn" -V clean test'
	}
	stage('package'){
		sh '"/opt/maven/bin/mvn" -V clean package'
	}
	 stage('Deploy to Tomcat'){
		 sshagent(['xnxnxnxn']) {
			 sh 'scp -o StrictHostKeyChecking=no target/*.war ec2-user@34.220.138.43:/opt/tomcat/webapps/'
      }
}
}
