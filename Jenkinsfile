pipeline {
    agent any
    parameters{
        choice(name = 'VERSION', choices = ['1.1', '1.2', '1.3], defaultvalue ='')
    }
    stages {
        stage('Build') {
            steps {
                echo "building application ${VERSION}"
            }
        }
        stage('test') {
            steps {
                echo "testing application ${VERSION}"
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying application'
            }
        }
    }
}
