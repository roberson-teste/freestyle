node {
	stage('BUILD') {
		try {
			build 'freestyle'
		} catch(e) {
			echo "ERROR: $e"
			emailextrecipients([[$class: 'DevelopersRecipientProvider'], [$class: 'CulpritsRecipientProvider'], [$class: 'RequesterRecipientProvider'], [$class: 'FailingTestSuspectsRecipientProvider'], [$class: 'FirstFailingBuildSuspectsRecipientProvider'], [$class: 'UpstreamComitterRecipientProvider']])
		}
	}
}
