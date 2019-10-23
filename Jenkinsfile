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
<<<<<<< HEAD
        sh 'echo ${BRANCH_NAME}'
        sh 'echo ${GIT_BRANCH}'
        sh 'echo ${GIT_LOCAL_BRANCH}'
=======
      }
    }
    stage('Merge PR') {
      when {
        branch 'PR-*'
      }
      steps {
        sh 'git remote set-url origin git@github.com:practicaljenkins/phptest.git'
        sh 'git remote set-branches --add origin ${CHANGE_TARGET}'
        sh 'git fetch origin'
        sh 'git checkout ${CHANGE_TARGET}'
        sh 'git merge --no-ff ${GIT_COMMIT}'
        sh 'git push origin ${CHANGE_TARGET}'
>>>>>>> 08d79dda3a7034e726797426445ba9d4eb1397b7
      }
    }
  }
}

