node {
   
    stage("Git") {
	   git 'https://github.com/javahometech/myweb'  
        }
		
        
    stage("Build") {
	
                    sh 'mvn clean package'
                   
                }
                sendMail(status)
                
            }

/**
* Sends Status Mail
*/
def sendMail(status){
if (status==0) {
mail bcc: '', 
body: """Build & deploy job completed success
Build Tag: $BUILD_TAG.
Jenkins URL: $JENKINS_URL
Please Test.

Regards,
DevOps Team""", 
cc: '', from: '', replyTo: '', subject: "Deployment Complete ", to: "vijaykumarbirru876@gmail.com"
} 
else {
mail bcc: '', 
body: """Build and deploy job failed for $ServiceName in $environment environment.
Build Tag: $BUILD_TAG.
Jenkins URL: $JENKINS_URL
Please check the logs.
Regards,
DevOps Team""", 
cc: '', from: '', replyTo: '', subject: "Deployment Failed ", to: "vijaykumarbirru876@gmail.com"
sh "exit 1"  
}
}
