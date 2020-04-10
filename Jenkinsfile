node {
    stage('Git'){
      git 'https://github.com/javahometech/myweb'    
      
      
      
      
      
    }
    
    stage('Maven Build'){
      sh 'mvn clea package'   
    }

    
    stage('Email'){
    
    mail bcc: '', body: '''Thanks,
Java Home''', cc: '', from: '', replyTo: '', subject: 'Pipeline vijay Demo', to: 'vijaykumarbirru876@gmail.com'





    }
}
