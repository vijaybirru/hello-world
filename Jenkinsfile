node {
    try {
    stage('Git'){
      git 'https://github.com/javahometech/myweb'   
    }
    stage('Maven Build'){
      sh 'mvn clea package'   
    }
    }
    catch (err) {
        echo "Caught: ${err}"
        println "Sending complete build status"
        emailtext body: '${BUILD_LOG, maxLines=35, escapeHtml=false}', subject: '${JOB_NAME}-${BUILD_NUMBER}', to: 'vijaykumarbirru876@gmail.com'
        currentBuild.result = 'FAILURE'
    }
}
