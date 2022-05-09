pipeline {
    agent { docker { image 'maven:3.8.4-openjdk-11-slim' } }
    stages {
        stage('build') {
            steps {
                sh 'mvn --version'
            }
        },
        stage('Upload') {
            dir('path/to/your/project/workspace'){
                pwd(); //Log current directory
                withAWS(region:'us-east-2',credentials: '$AKIAVKJB5VEHMTPA3W4B') {
                    def identity=awsIdentity();//Log AWS credentials

                    // Upload files from working directory 'dist' in your project workspace
                    s3Upload(bucket:"amex-interview-bucket-5-9-22", workingDir:'/', includePathPattern:'**/*');
                }

            };
        }
    }
}
