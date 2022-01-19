pipeline {
  agent {
    docker {
      image 'maven:3.3.9-jdk-8'
    }

  }
  stages {
    stage('') {
      steps {
        sh '''pipeline {
  agent {
    docker {
      image \'maven:3.3.9-jdk-8\'
    }

  }
  stages {
    stage(\'build\') {
      parallel {
        stage(\'Test\') {
          steps {
            sh \'mvn test -Dtest=!*API*\'
          }
        }

        stage(\'build\') {
          steps {
            sh \'mvn -B -DskipTests=true package\'
          }
        }

        stage(\'Acceptance Test\') {
          steps {
            sh \'mvn test\'
          }
        }

      }
    }
  }
}'''
        }
      }

    }
  }