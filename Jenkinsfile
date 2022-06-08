pipeline{
    agent{ 'lable python_build'}
    stages(scm){
        steps{
            git branch: master , url :'https://github.com/jellapu/python.git'
        }
    }
    stage('installing depandencies') {
            steps {
                    sh 'pip install '
                }
            }
            stage('installing depandencies') {
            steps {
                    sh 'pip install flake8 '
                }
            }
            stage('test') {
            steps {
                    sh 'pytest '
                }
            }
            stage('run test with flake') {
            steps {
                    sh 'flake8 . '
                }
            }
}