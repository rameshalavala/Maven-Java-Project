#!groovy

node {
    currentBuild.result = "SUCCESS"

    try {

       stage('Checkout'){

          checkout scm
       }

       stage('Compiling'){

          sh 'mvn clean install'
       }
	   
      stage('Sonar') {
                    //add stage sonar
                    sh 'mvn sonar:sonar'
                }
	  /* stage('Deploy') {
                    
                    sh 'mvn sonar:sonar'
                }*/
	   
	stage('Checkstyle') {
                    sh 'mvn checkstyle:checkstyle'
                }

               stage('PMD') {
                    sh 'mvn pmd:check'
                }
      /* stage('mail'){

         mail body: 'project build successful',
                     from: 'abc@gmail.com',
                     replyTo: 'xyz@gmail.com',
                     subject: 'project build successful',
                     to: 'xyz@gmail.com'
       }*/
	    
	    

    }
    catch (err) {

        currentBuild.result = "FAILURE"

           /* mail body: "project build error is here: ${env.BUILD_URL}" ,
            from: 'abc@gmail.com',
            replyTo: 'xyz@gmail.com',
            subject: 'project build failed',
            to: 'xyz@gmail.com'
            */
        throw err
    }
}
