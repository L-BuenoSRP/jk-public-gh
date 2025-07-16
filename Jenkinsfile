pipeline {
    agent any

    stages {
        stage('Git Clone') {
            steps {
                git branch: 'main', url: 'https://github.com/L-BuenoSRP/jk-public-gh'
            }
        }
        stage('Docker Build') {
            steps {
                sh 'docker build -t webapp:${BUILD_NUMBER} .'
            }
        }
        stage('Docker Run') {
            steps {
                // sh 'docker stop webapp'
                // sh 'docker run -d --rm -p 3001:3000 --name webapp webapp:${BUILD_NUMBER}'
                sh '''
                # docker stop webapp
                docker run -d --rm -p 3001:3000 --name webapp webapp:${BUILD_NUMBER}
                '''
            }
        }
    }
}
