pipeline {
    agent any

    stages {
        stage('Get Source Code') {
            steps {
                git credentialsId: '914c6afa-b5f9-43be-b549-ff43b70a1816', url: 'https://github.com/gdnam/project9.git'
                echo 'Hello World'
            }
        }
    stages('Build code')
    {
        steps
        {
            bat script: 'mvn complie'
        }
    }
    stages('run test')
    {
        steps{
            bat script: 'mvn test -Dbrower=localchrome'
        }
    }
    stages('Publish HTML Reports')
    {
        steps
        {
            publishHTML([allowMissing: false, alwaysLinkToLastBuild: true, keepAll: true, reportDir: '', reportFiles: 'target/surefire-reports/index*.html', reportName: 'Pipeline', reportTitles: '', useWrapperFileDirectly: true])
        }
    }
    }
}