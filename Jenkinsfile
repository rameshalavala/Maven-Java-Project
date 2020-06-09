#!groovy

node {
        stage('scm Checkout'){

          git 'https://github.com/rameshalavala/Maven-Java-Project'
       }

       stage('Compiling'){

          sh 'mvn clean install package'
       }
	   
      stage('Sonar') {
                    //add stage sonar
                    sh 'mvn sonar:sonar'
                }
	stage('artifact') {
                    //add stage sonar
                    archive 'target/*.war'
                }
}
