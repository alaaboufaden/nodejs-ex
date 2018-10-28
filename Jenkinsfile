#!/usr/bin/env groovy
node {
    stage('checkout') {
        checkout scm
    }

    stage('Build') {
       sh '/usr/bin/oc start-build spring-petclinic'
    }

    stage('Deploy') {
       sh ' /usr/bin/oc deploy spring-petclinic --latest'
    }
}
