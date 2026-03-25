pipeline {
    agent {
        label 'podman'
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building the node app'
                sh '''
                    ls -lart
                    node -v
                    npm -v
                    npm ci
                    npm run build
                    ls -lart
                '''
            }
        }
    }
    
    stage('Test') {
        steps {
            echo "Test stage"
            sh 'test -f build/index.html'

        }
    }
}