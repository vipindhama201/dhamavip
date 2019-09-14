#!/usr/bin/env groovy
import hudson.model.*
import java.net.URL

node{
    stage('Git Checkout'){
	     git 'https://github.com/vipindhama201/DevOpsClassCodes.git'
    }
	stage('Compile'){
	    withMaven(maven:'My Maven'){
		    sh 'mvn compile'
	    }
	}
    stage('Test'){
     	try{
		     withMaven(maven:'My Maven'){
			     sh 'mvn test'
			 }
        } finally{
             junit 'target/surefire-reports/*.xml'
        }
    }
	stage('Package'){
	    withMaven(maven:'My Maven'){
		    sh 'mvn package'
		}
	}
}	
