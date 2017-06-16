#!/usr/bin/env groovy

node {
    stage('checkout') {
        checkout scm
    }

    docker.image('maven:3.5.0-jdk-8').inside('-u root') {
    
	stage('check java') {
            sh "java -version"
        }
	
	stage('verify') {
	    sh 'mvn -version'
	}
	
	stage('clean') {
            sh 'mvn clean'
        }
	
	stage('backend tests') {
            sh  'mvn test'
        }

        stage('packaging') {
            sh 'mvn package -DskipTests'
        }
	
	stage('docker build') {
	    sh 'mvn docker:build'
	}

	stage('publish docker') {
            docker.withRegistry('http://localhost:5000', 'docker-registry-local') {
                dockerImage.push 'latest'
            }
        }

    }
}
