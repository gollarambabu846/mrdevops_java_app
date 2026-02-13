@Library('my-shared-library')
pipeline {
    agent any

    stages {

        stage('Git Checkout') {
            steps {
            gitCheckout{
                branch : "main"
                url: "https://github.com/gollarambabu846/mrdevops_java_app.git"
              }    
        
            }
        }
    }
}
