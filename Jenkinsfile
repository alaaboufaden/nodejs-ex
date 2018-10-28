#!/usr/bin/env groovy
node {
    stage('checkout') {
        checkout scm
    }

    stage('Build') {
        openshiftBuild(namespace: 'ci', buildConfig: 'spring-petclinic', showBuildLogs: 'true')
    }

    stage('Deploy') {
    openshiftDeploy(namespace: 'ci', deploymentConfig: 'spring-petclinic')
    }
}
