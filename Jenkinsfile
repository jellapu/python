pipeline{
    agent{label 'build_java_11'}
    stages{
        stage(SCM){
            steps{
                git branch: 'master', url: 'https://github.com/jellapu/python.git'
            }
        }
        stage('build'){
            steps{
                sh "pip install -r requirements.txt"
            }
        }
        stage('test'){
            steps{
                sh "pip install pytest pytest-azurepipelines"
                sh "pip install pytest-cov"
                sh "/home/jenkins/.local/bin/pytest --doctest-modules --junitxml=junit/test-results.xml --cov=. --cov-report=xml"
            }
        }
        stage('publish reporting'){
            steps{
                junit testResults: '**/test-*.xml'
            }
        }
    }
}