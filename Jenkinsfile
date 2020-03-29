pipeline {
    agent any
    environment {
        LIBRARY_REPOSITORY = 'https://github.com/kinlhp/jenkins-library-dynamic-loading.git'
    }
    stages {
        stage('load') {
            steps {
                // It is best to refer to Pipeline Syntax for the precise syntax for your SCM: https://jenkins.io/doc/pipeline/steps/workflow-cps-global-lib
                library([
                    identifier: 'bar@master',
                    retriever: modernSCM([
                        scm: [
                            $class: 'GitSCMSource',
                            remote: "${LIBRARY_REPOSITORY}"
                        ]
                    ])
                ])
            }
        }
        stage('greet') {
            steps {
                foo([:])
                foo([name: 'Steve'])
            }
        }
    }
}
