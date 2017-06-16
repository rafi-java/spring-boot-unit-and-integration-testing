#!/usr/bin/env groovy

node {
    stage('checkout') {
        checkout scm
    }

    docker.image('openjdk:8').inside('-u root') {
    
stages {
	stage('check java') {
            sh 'java -version'
        }
	
	stage('verify') {
	    sh 'mvn -version'

        stage('clean') {
            sh 'mvn clean'
        }

        stage('backend tests') {
            sh 'mvn test'
        }

        stage('packaging') {
            sh 'mvn package -DskipTests'
        }
    }

    }
}
