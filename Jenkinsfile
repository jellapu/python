pipeline{
    agent{label 'build_java_11'}
    stages{
        stage(SCM){
            steps{
                git branch: 'main', url: 'https://github.com/jellapu/python.git'
            }
        }
        stage('install the dependencies'){
            steps{
                sh "pip install"
            }
        }
        stage('install the dependencies'){
            steps{
                sh "pip install flake8"
            }
        }
        stage('test'){
            steps{
                sh "pytest"
            }
        }
        stage('run test with flake'){
            steps{
                sh "flake8 . "
            }
        }
    }
}