pipeline {
  agent {
    label "jenkins-maven-java11"
  }
  environment {
    ORG = 'painyjames'
    APP_NAME = 'self_service'
    CHARTMUSEUM_CREDS = credentials('jenkins-x-chartmuseum')
    DOCKER_REGISTRY_ORG = 'painyjames'
  }
  stages {
    stage('CI Build and push snapshot') {
      environment {
        PREVIEW_VERSION = "0.0.0-SNAPSHOT-$BRANCH_NAME-$BUILD_NUMBER"
        PREVIEW_NAMESPACE = "$APP_NAME-$BRANCH_NAME".toLowerCase()
        HELM_RELEASE = "$PREVIEW_NAMESPACE".toLowerCase()
      }
      steps {
        container('maven') {
          echo FOO
        }
      }
    }
  }
}