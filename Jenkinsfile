pipeline {
    agent any
    stages {
        stage ('SCM') {
            steps {
                git(url: 'https://github.com/pavansw/simpleMavenJunit.git', branch: 'master', poll: true)
            }
        }
        stage ('Compile') {
            steps {
                sh 'mvn compile'
            }
        }
        stage ('Testing') {
            steps {
                sh 'mvn test'
            }
        }
        stage ('Package') {
            steps {
                sh 'mvn package'
            }
        }
        stage ('QA Run Jar Package') {
            steps {
                sh 'java -jar target/gs-maven-0.1.0.jar'
            }
        }
    }
}
