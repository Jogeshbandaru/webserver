pipeline {
	agent any

		stages {
		    stage('SCM checkout') {
			steps {
			     git url: 'https://github.com/Jogeshbandaru/webserver.git'
			       }
			}

		    stage('Archiving artifacts') {
			 steps {
				archiveArtifacts '**/*.html'
				}
			}
		
		    stage('transfer Artifacts') {
			 steps {
				sshPublisher(publishers: [sshPublisherDesc(configName: 'Jenkin-Webserver', transfers: [sshTransfer(excludes: '', execCommand: '', execTimeout: 120000, flatten: true, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: '/var/www/html', remoteDirectorySDF: false, removePrefix: '', sourceFiles: '*.war')], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])
				}
  			}
    }
}
