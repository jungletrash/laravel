node('php'){
    stage('Clean'){
        deleteDir()
        sh 'ls -la'
    }

    stage('Fetch') {
        checkout scm
    }

    stage('Docker Build') {
        sh 'docker build -t jungletrash/laravel:$BUILD_NUMBER .'
    }

    stage('Docker Ship') {
        sh 'docker push jungletrash/laravel:$BUILD_NUMBER'
    }
    
    stage('Docker Clean') {
        sh 'docker rmi -f jungletrash/laravel:$BUILD_NUMBER'
    }
}
