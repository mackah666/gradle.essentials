pipeline {
  agent any
  stages {
    stage('Pre Clean') {
      steps {
        echo 'Pre Cleaning'
      }
    }
<<<<<<< HEAD
   
    stage('Oops stage') {
      	steps {
		echo 'Oops all over this'
	}

    }
    
=======
>>>>>>> 378056a8394d829cd9e8517fa765f0244abb94eb
    stage('Clean Previous Android Builds') {
      steps {
        echo 'Clean Previous Android Builds'
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
<<<<<<< HEAD
    // Changeset log working correctly
    stage('ChangeLog') {
      steps {
        script{
           echo 'Npm Audit'
          def changeLogSets = currentBuild.changeSets
          println(changeLogSets)
          // def clogs = changeLogSets()
          // echo clogs
        }
      }         
    }
=======
>>>>>>> 378056a8394d829cd9e8517fa765f0244abb94eb
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
  }
<<<<<<< HEAD
}

def changeLogSets() {
 def changeLogSets = currentBuild.changeSets
    for (int i = 0; i < changeLogSets.size(); i++) {
        def entries = changeLogSets[i].items
        for (int j = 0; j < entries.length; j++) {
            def entry = entries[j]
            echo "${entry.commitId} by ${entry.author} on ${new Date(entry.timestamp)}: ${entry.msg}"
            def files = new ArrayList(entry.affectedFiles)
            for (int k = 0; k < files.size(); k++) {
                def file = files[k]
                echo "  ${file.editType.name} ${file.path}"
        }
    }
}
}

=======
}
>>>>>>> 378056a8394d829cd9e8517fa765f0244abb94eb
