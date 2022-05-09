pipeline {
    agent { docker { image 'maven:3.8.4-openjdk-11-slim' } }
    stages {
        stage('build') {
            steps {
                sh 'echo "Hello World!'
            }
        }
        stage('artifacts to s3') {
            steps {
                s3Upload acl: 'Private',
                    bucket: 'amex-interview-bucket-5-9-22',
                    cacheControl: '',
                    excludePathPattern: '',
                    file: '*',
                    includePathPattern: '',
                    metadatas: [''],
                    path: '/',
                    redirectLocation: '',
                    sseAlgorithm: '',
                    tags: '',
                    text: ''
            }
        }
    }
}
