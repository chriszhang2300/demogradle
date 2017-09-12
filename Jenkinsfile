pipeline {
     agent any
	 triggers {
		 pollSCM('* * * * *')
	}
     stages {
	 /*
        stage("Checkout") {
               steps {
                    git url: 'https://github.com/chriszhang2300/demogradle.git'
               }
        }
		*/
        stage("Compile") {
                 steps {
                     bat "dir"

                     bat "./gradlew.bat compileJava"
                 }
        }
        stage("Unit test") {
            steps {
                bat "./gradlew.bat test"
            }
        }
		
		stage("Code coverage") {
			steps {
				  bat "./gradlew.bat jacocoTestReport"
				   publishHTML (target: [
					   reportDir: 'build/reports/jacoco/test/html',
					   reportFiles: 'index.html',
					   reportName: "JaCoCo Report"
				  ])
				  bat "./gradlew.bat jacocoTestCoverageVerification"
			 }
		}
          
     }     
}