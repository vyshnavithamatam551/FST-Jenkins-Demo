pipeline {
    agent any

    stages {
        stage("Build") {
            steps {
                sh "mvn compile"
            }
        }

        stage("Test") {
            steps {
                wrap([$class: 'Xvfb', debug: true, displayName: 34, displayNameOffset: 0, timeout: 10]) {
                    sh "mvn test"
                }
            }
        }

        stage("Publish") {
            steps {
                testNG()
            }
        }
    }
}
