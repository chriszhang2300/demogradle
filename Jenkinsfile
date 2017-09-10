pipeline {
     agent any
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
          
     }     
}