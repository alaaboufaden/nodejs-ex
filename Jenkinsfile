#!/usr/bin/env groovy
node {
    stage('checkout') {
        checkout scm
    }

    stage('Build') {
       sh './oc start-build spring-petclinic -F'
    }

    stage('Deploy') {
       sh ' ./oc deploy spring-petclinic --latest'
    }
}
