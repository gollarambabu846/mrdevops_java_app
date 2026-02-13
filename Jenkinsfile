@Library('my-shared-library') _

pipeline {
    agent any
    
    environment {
        // Keeps Java 17+ from blocking Maven's compiler access
        MAVEN_OPTS = "--add-opens java.base/java.lang=ALL-UNNAMED --add-opens jdk.compiler/com.sun.tools.javac.processing=ALL-UNNAMED"
    }

    stages {
        stage('Git Checkout') {
            steps {
                script {
                    gitCheckout(
                        branch: 'main',
                        url: 'https://github.com/gollarambabu846/mrdevops_java_app.git'
                    )
                }
            }
        }

        stage('Build') {
            steps {
                script {
                    mvnBuild() 
                }
            }
        }

        stage('Unit Test') {
            steps {
                script {
                    mvnTest()
                }
            }
        }

        stage('Integration Test') {
            steps {
                script {
                    mvnIntegrationTest()
                }
            }
        }
    }
}