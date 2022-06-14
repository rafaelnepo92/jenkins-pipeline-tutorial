pipeline {
    agent {
        label 'maven'
    }
    parameters {
         booleanParam description: 'limpar o workspace antes de limpar o build', name: 'CLEAN_BEFORE_BUILD'
    }

    stages {
        stage('Clean') {
            when {
                expression {params.CLEAN_BEFORE_BUILD}
            }
            steps {
             echo 'Stage Clean'
            }
        }
        stage('Build') {
            steps {
            sh 'mvn compile'
            }
        }

    stage('Test') {
        steps {
            sh 'mvn verify'
            }
        }

    }   

}
