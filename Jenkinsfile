pipeline {
    agent {
        label 'master'
    }
    stages {
        stage('SPARQL Tests') {
            steps {
                sh 'java -cp lib/sparql.jar uk.org.floop.sparqlTestRunner.Run -i -s https://production-drafter-ons-alpha.publishmydata.com/v1/sparql/live'
            }
        }
    }
    post {
        always {
            junit 'reports/**/*.xml'
        }
    }
}
