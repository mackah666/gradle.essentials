pipeline {
  agent any
  stages {
    stage('Pre Clean') {
      parallel {
        stage('Pre Clean') {
          steps {
            echo 'Pre Cleaning'
          }
        }
        stage('Clean Previous Android Builds') {
          steps {
            echo 'Clean Previous Android Builds'
          }
        }
        stage('Third Task') {
          steps {
            echo 'Hello'
          }
        }
      }
    }
    stage('Update Build Display') {
      steps {
        echo 'Update Build Display'
      }
    }
    stage('Update Checkout Specific Tag for Picknmix android') {
      steps {
        echo 'Update Checkout Specific Tag for Picknmix android'
      }
    }
    stage('Npm Install-Android') {
      steps {
        echo 'Npm Install-Android'
      }
    }
    stage('Npm Audit') {
      steps {
        echo 'Npm Audit'
      }
    }
    stage('GMI Android Library Tests') {
      steps {
        echo 'GMI Android Library Tests'
      }
    }
    stage('Framework Android Unit Tests') {
      steps {
        echo 'Framework Android Unit Tests'
      }
    }
    stage('Copy bundled game') {
      steps {
        echo 'Copy bundled game'
      }
    }
    stage('Initialise') {
      steps {
        script {
          def artifact = "getCreative/release/1.2.7/ios/1.2.7-origin-release.1+9/getCreative-Production-1.2.7-RC3.ipa"
          build(job: 'Deployment/Develop', parameters: [[$class: 'StringParameterValue', name: 'ParamA', value: artifact], [$class: 'StringParameterValue', name: 'ParamB', value: "paramBValue"]], wait: false)
        }
      }
    }
  }
}
