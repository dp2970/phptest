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
    stage('Merge PR'){
      when{
        branch 'PR-*'
    }
      steps{
        sh 'echo ${BRANCH_NAME}'
        sh 'echo ${GIT_BRANCH}'
        sh 'echo ${GIT_LOCAL_BRANCH}'
      }
    }
  }
}

