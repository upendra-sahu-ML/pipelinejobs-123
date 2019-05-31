pipeline {
    agent {
      label "jenkins-jx-base"
    }
    environment {
      ORG               = 'tnahak'
      APP_NAME          = 'newpipeline123'
      CHARTMUSEUM_CREDS = credentials('jenkins-x-chartmuseum')
    }
    stages {
      stage('Build Release') {
        when {
          branch env.BRANCH_NAME
        }
        steps {
          container('jx-base') {
            // ensure we're not on a detached head
            sh "echo newpipeline change"
          }
        }
      }
    }
    post {
        always {
            cleanWs()
        }
    }
  }
