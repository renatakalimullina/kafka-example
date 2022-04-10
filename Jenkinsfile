pipeline {
    agent any
options {
        timestamps()
        skipDefaultCheckout(true)
	}
    stages {
        stage('Check docker and docker-compose version') {
            steps {
                sh 'docker --version'
                sh 'docker-compose --version'
				}
			}
        stage('Clone github repository') {
            steps {
                cleanWs()
                sh 'git clone https://github.com/renatakalimullina/kafka-example'
				sh 'cd kafka_conf'
                }
			}
        stage('Start docker containers') {
            steps {
                sh 'docker-compose up -d'
            }
        }
    }
}
