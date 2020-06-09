#!groovy

node {   
	stage('Checkout'){
git 'https://github.com/LovesCloud/java-tomcat-maven-example'
       }

       stage('package'){
          // build step
          def mvnHome = tool name: 'maven 3.6.3', type: 'maven'
	sh "${mvnHome}/bin/mvn package"
       }
	stage('deploy'){
          // build step
          def mvnHome = tool name: 'maven 3.6.3', type: 'maven'
	sh "${mvnHome}/bin/mvn deploy"
	}
	
}
