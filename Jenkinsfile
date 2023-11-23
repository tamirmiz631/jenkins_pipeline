pipeline {
    agent any
    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
                echo 'Another commit'
            }
        }
        stage('Goodbay'){
            steps {
                echo 'Goodbay'
                mail bcc: '', body: 'you have a problem  ', cc: '', from: '', replyTo: '', subject: 'problem', to: 'tamirmiz03@gmail.com'
            }
        }
    }
    post {
        success {
            mail bcc: '', body: 'good ', cc: '', from: '', replyTo: '', subject: 'good', to: 'tamirmiz03@gmail.com'
        }
        failure {
            step([$class: 'Mailer', notifyEveryUnstableBuild: true, recipients: 'tamirmiz03@gmail.com', sendToIndividuals: false])
        }
    }
}
