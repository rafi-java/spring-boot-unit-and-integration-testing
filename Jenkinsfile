#!/usr/bin/env groovy

node {
    stage('checkout') {
        checkout scm
    }

    docker.image('maven:3.3-jdk-8').inside('-u root') {
    
	stage('check java') {
            sh "java -version"
        }
	
	stage('verify') {
	    sh 'mvn -version'
	}
	
	stage('clean') {
            sh 'mvn clean'
        }

    }
}
