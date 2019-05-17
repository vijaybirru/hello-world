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
      sshPublisher(publishers: [sshPublisherDesc(configName: 'TOmcat', transfers: [sshTransfer(cleanRemote: false, excludes: '', execCommand: '', execTimeout: 120000, flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: '/opt/tomcat/webapps/', remoteDirectorySDF: false, removePrefix: '', sourceFiles: '\'/var/lib/jenkins/workspace/Jenkins file1/target/**/*.jar\'')], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])
   }
}
