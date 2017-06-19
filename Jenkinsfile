#!/usr/bin/env groovy

node {
    stage('checkout') {
        checkout scm
    }

    //docker.image('maven:3.5.0-jdk-8').inside('-v /tmp/m2:/home/mrafi/.m2') {
    
	stage('check java') {
            sh "java -version"
	    sh 'export DOCKER_HOST=https://192.168.42.247:2376'
            sh 'export DOCKER_API_VERSION=1.23'
	sh 'export DOCKER_TLS_VERIFY=1'
	sh 'export DOCKER_CERT_PATH=/home/mrafi/.minikube/certs'
        }
	
	stage('verify') {
	    sh 'mvn -version'
	}
	
	//stage('clean') {
        //    sh 'mvn clean'
        //}
	
	//stage('backend tests') {
        //    sh  'mvn test'
        //}

        //stage('packaging') {
        //    sh 'mvn package -DskipTests'
        //}
	
	stage('docker build') {
	    sh 'mvn clean package -DskipTests=true docker:build'
	    sh 'echo $USER'
            //docker.withRegistry('http://localhost:5000', 'docker-registry-local') {
                //dockerImage.push 'latest'
		//docker.image('microservice/spring-boot-testing-levels').push 'latest'
            //}
	}

	//stage('publish docker') {
        //    docker.withRegistry('http://localhost:5000', 'docker-registry-local') {
        //        dockerImage.push 'latest'
        //    }
       // }

    //}
}
