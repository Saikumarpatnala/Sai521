pipeline {
    agent any

    stages {
        stage('clne scm code') {
            steps {
                echo 'cloning code from github'
		        git 'https://github.com/wakaleo/game-of-life.git'
            }
        }
        stage('displaying code') {
            steps {
                echo 'displaying code'
		        sh 'ls -lrth'
            }
        }
        stage('build code') {
            steps {
                echo 'builing the code'
		        sh 'mvn clean install'
            }
        }
        stage('deploying code') {
            steps {
                echo 'deploying in tomcat'
		        deploy adapters: [tomcat9(credentialsId: '360e0d6e-b8c6-4d7b-b4be-fb9d79568bae', path: '', url: 'http://13.234.113.236:8080/')], contextPath: 'batch-5', war: '**/*.war'
            }
        }
    }
}
