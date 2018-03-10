pipeline {

  agent {
    node {
      label 'master'
    }
  }

  options {
    timestamps()
  }

  stages {
    stage('PHPUnit Test') {
      steps {
        echo 'Running PHPUnit...'
        sh '/bin/phpunit ${WORKSPACE}'
      }
    }
    stage('JIRA') {
      steps {
        script {
          def issue = jiraGetIssue idOrKey: ${GIT_BRANCH}, site: 'practical-jenkins-jira'
          echo issue.data.toString()
        }
      }
    }
  }
}

