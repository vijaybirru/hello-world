node {
    try {
    emailext body: 'Jenkins job started !!!!!!!', subject: 'Email Notification for starting jenkins job', to: 'vijaykumarbirru876@gmail.com'
    stage('Git'){
      git 'https://github.com/javahometech/myweb'  
    }
    stage('Maven Build'){
      sh 'mvn clean packagwe'   
    }
    }
    catch (err) {
        echo "Caught: ${err}"
        println "Sending complete build status"
        currentBuild.result = 'FAILURE'
		emailext body: '''${SCRIPT, template="groovy-html.template"}''',
        mimeType: 'text/html',
        subject: "[Jenkins] ${JOB_NAME}-${BUILD_NUMBER}",
        to: "Vijaykumarbirru876@gmail.com"
    }
}
