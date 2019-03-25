@Library('groovy-slack') _
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
    
    stage('Change Log'){
      steps {
        script {
         def changeLog = getChangeLog()
         echo changeLog
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
        echo 'Copy bundled game content'
      }
    }
    stage('Initialise') {
      steps {
        script {
          def normal = "picknmixDemoApp/develop/android/2.18.4-origin-develop.1+319/picknmix-normal-debug.apk"
	  def freetime  = "picknmixDemoApp/develop/android/2.18.4-origin-develop.1+319/picknmix-freetime-debug.apk"
          //def dSYMs = "dumpingGround/release/1.5.1/ios/1.5.1-origin-release.1+0/dumpingGround-Enterprise-1.3-RC3-dSYMs.zip"
          def app = "picknmixDemoApp/develop/android/2.18.4-origin-develop.1+319/"
          build(job: 'Deployment', parameters: [[$class: 'StringParameterValue', name: 'normal', value: normal],
							[$class: 'StringParameterValue', name: 'freetime', value: freetime], 
                                                    
                                                        [$class: 'StringParameterValue', name: 'app', value: app]], wait: false)
        }
      }
    }
  }
   //post {
   //     always {
   //       script{
	        /* Use slackNotifier.groovy from shared library and provide current build result as parameter */   
            //slackNotifier(currentBuild.currentResult, getChangeLog())
   //       }
   //     }
   // }
}


@NonCPS
def getChangeLog() {
    def changeLogSets = currentBuild.changeSets

    def changeLog = ""
    for (int i = 0; i < changeLogSets.size(); i++) {
        def entries = changeLogSets[i].items
        for (int j = 0; j < entries.length; j++) {
            def entry = entries[j]
            changeLog += "${entry.author}: ${entry.msg}"
            def files = new ArrayList(entry.affectedFiles)
            for (int k = 0; k < files.size(); k++) {
                def file = files[k]
                changeLog += "\n"
                changeLog += "\t${file.editType.name} ${file.path}"
            }
            changeLog += "\n"
        }
    }
    changeLog = changeLog.trim()
    if (!changeLog) {
        changeLog = "No change log"
    }
    changeLog = java.net.URLEncoder.encode(changeLog, "UTF-8")
    return changeLog
}
