pipeline {
    agent any
    
    environment {
        // We are adding "util" and "code" exports to fix the Lombok access error
        MAVEN_OPTS = """
            --add-opens java.base/java.lang=ALL-UNNAMED 
            --add-opens jdk.compiler/com.sun.tools.javac.processing=ALL-UNNAMED 
            --add-opens jdk.compiler/com.sun.tools.javac.util=ALL-UNNAMED 
            --add-opens jdk.compiler/com.sun.tools.javac.code=ALL-UNNAMED 
            --add-opens jdk.compiler/com.sun.tools.javac.main=ALL-UNNAMED 
            --add-opens jdk.compiler/com.sun.tools.javac.model=ALL-UNNAMED
        """
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
        // ... rest of your stages
    }
}