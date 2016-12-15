properties([disableConcurrentBuilds()])

node {

	stage('BUILD') {
		checkout scm
		//checkout()
	}

	stage('BUILD') {
        try {
		    buildAll()
        } finally {
            sendEmails()
        }
	}

}

def checkout() {
	checkout scm
    git credentialsId: '36c82770-bc0c-46ac-a769-acaf0650e411', url: 'https://github.com/roberson-teste/freestyle.git'
}

def buildAll() {
    echo 'sleeping'
	sh 'ping 127.0.0.1 -n 8 > nul'
	echo 'waking up'
	echo 'awake'
}

def sendEmails() {
        echo 'CulpritsRecipientProvider'
        emailext body: 'You have broken the job!', recipientProviders: [[$class: 'CulpritsRecipientProvider']], subject: 'BROKEN JOB CulpritsRecipientProvider'
        echo 'DevelopersRecipientProvider'
        emailext body: 'You have broken the job!', recipientProviders: [[$class: 'DevelopersRecipientProvider']], subject: 'BROKEN JOB DevelopersRecipientProvider'
        echo 'RequesterRecipientProvider'
        emailext body: 'You have broken the job!', recipientProviders: [[$class: 'RequesterRecipientProvider']], subject: 'BROKEN JOB RequesterRecipientProvider'
        echo 'FailingTestSuspectsRecipientProvider'
        emailext body: 'You have broken the job!', recipientProviders: [[$class: 'FailingTestSuspectsRecipientProvider']], subject: 'BROKEN JOB FailingTestSuspectsRecipientProvider'
        echo 'FirstFailingBuildSuspectsRecipientProvider'
        emailext body: 'You have broken the job!', recipientProviders: [[$class: 'FirstFailingBuildSuspectsRecipientProvider']], subject: 'BROKEN JOB FirstFailingBuildSuspectsRecipientProvider'
        echo 'UpstreamComitterRecipientProvider'
        emailext body: 'You have broken the job!', recipientProviders: [[$class: 'UpstreamComitterRecipientProvider']], subject: 'BROKEN JOB UpstreamComitterRecipientProvider'
}
