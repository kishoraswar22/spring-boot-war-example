pipeline {
    agent any

    tools{

        maven 'maven'
    }

    stages {
        stage('Code Checkout') {
            steps {
                  git branch: 'master', changelog: false, poll: false, url: 'https://github.com/kishoraswar22/spring-boot-war-example.git'         
            }
        }
    stage('Build') {
            steps {
                sh 'mvn package -Dmaven.test.skip=true'
            }
        }
    stage('Test') {
            steps {
                echo 'Hello World'
            }
        }

     stage('Deploy To Dev') {
            steps {
                deploy adapters: [tomcat9(credentialsId: 'tomcat_user', path: '', url: 'http://13.233.193.236:8080/')], contextPath: null, onFailure: false, war: '**/*.war'
            }
        }

     stage('Deploy To Uat') {
            steps {
                echo 'Hello World'
            }
        }
     stage('Prod Deployment') {
            steps {
                echo 'Hello World'
            }
        }
    }
}
