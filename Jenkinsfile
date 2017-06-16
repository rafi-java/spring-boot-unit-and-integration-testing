pipeline {
    agent any 
    tools {
        maven 'mvn'
        jdk 'jdk8'
   }
    environment {
        DISABLE_AUTH = 'true'
       // DB_ENGINE    = 'sqlite'
//	-- AWS_ACCESS_KEY_ID     = credentials('AWS_ACCESS_KEY_ID')
  //      -- AWS_SECRET_ACCESS_KEY = credentials('AWS_SECRET_ACCESS_KEY')
    }
    stages {
        stage('build') {
            steps {
                sh 'mvn --version'
                sh 'java -version'
		sh 'mvn package -DskipTests=true'
		input 'Publish?'
		
		/*
		Publish?
		Proceed or Abort
		Approved by admin
		*/
            }

        }
	/*stage('printvar') {
            steps {
                sh 'printenv'
		 echo "PATH = ${PATH}"
                    echo "M2_HOME = ${M2_HOME}"
            }
        }*/
/*@Grab('org.apache.commons:commons-math3:3.4.1')
import org.apache.commons.math3.primes.Primes
void parallelize(int count) {
  if (!Primes.isPrime(count)) {
    error "${count} was not prime"
  }
  // …
}*/
    }
}

