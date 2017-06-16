#!/usr/bin/env groovy

node {
    stage('checkout') {
        checkout scm
    }

    docker.image('openjdk:8').inside('-u root') {
    
	
	stage('verify') {
	    sh 'mvn -version'
	}

    }
}
