pipeline {
  agent any
  stages {
    stage('Create Image Builder') {
      when {
        expression {
          openshift.withCluster() {
            return !openshift.selector("ci", "spring-petclinic").exists();
          }
        }
      }
      steps {
        script {
          openshift.withCluster() {
            openshiftBuild(namespace: 'ci', buildConfig: 'spring-petclinic', showBuildLogs: 'true')
          }
        }
      }
    }
    stage('Promote to DEV') {
      steps {
        script {
          openshift.withCluster() {
            openshiftDeploy(namespace: 'ci', deploymentConfig: 'spring-petclinic')
          }
        }
      }
    }
  }
}
