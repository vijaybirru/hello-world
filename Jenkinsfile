node {
    try {
    emailext body: 'Jenkins job started !!!!!!!', subject: 'Email Notification for starting jenkins job', to: 'vijaykumarbirru876@gmail.com'
    stage('Git'){
      git 'https://github.com/javahometech/myweb'   
    }
    stage('Maven Build'){
      sh 'mvn clean packag'   
    }
    stage('Email'){
    
    mail bcc: '', body: '''Thanks,
Java Home''', cc: '', from: '', replyTo: '', subject: "[Jenkins] ${JOB_NAME}-${BUILD_NUMBER}" SUCCESS, to: 'vijaykumarbirru876@gmail.com'''
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
