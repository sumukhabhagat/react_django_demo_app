pipeline {
    agent any
    
    stages {
        stage('Code') {
            steps {
                git branch: 'main', url: 'https://github.com/sumukhabhagat/react_django_demo_app.git'
            }
        }
        stage('Test') {
            steps {
                echo "Testing"
            }
        }
        stage("Build") {
            steps {
            script {
                sh "sudo docker build --no-cache -t react_django_demo_app ."
            }
        }
        }
        stage("Deploy") {
            steps {
            script {
                sh " sudo docker run -p 8001:8001 -d react_django_demo_app"
            }
        }
    }
}
}
