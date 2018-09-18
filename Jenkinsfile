pipeline {
   agent any
	options {
	buildDiscarder(logRotator(numToKeepStr: '2',artifactnumToKeepStr:'1'))
		}
	    stages {

	      stage('build'){
	                  steps{
	                     sh 'ant -f build.xml'
                                }
 
                           }
		stage('unit Test'){
		 steps{
	            sh 'ant -f test.xml'
			junit 'reports/results.xml'
                     }


               
	                       	  }
	           }
         

post{
	always{
		archiveArtifacts artifacts: 'dist/*.jar', fingerprint: true
		}
    }
    
         }
