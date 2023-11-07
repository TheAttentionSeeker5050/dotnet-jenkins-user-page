pipeline {
    agent any
    stage('Test') {
        steps {
            script {
                
                // assert if the server is up and serving the main page, passing if the response code is 200
                sh 'curl -I http://webserver | grep "HTTP/1.1 200 OK"'
            }
        }
    }
}
