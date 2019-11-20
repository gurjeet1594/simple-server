pipeline {
    agent any
    stages {
                stage('Test Environment') {
                    steps {
                            sh 'mvn test -Dtest=ControllerAndServiceSuite'
                    sh 'mvn test -Dtest=IntegrationSuite'
                        }
                }
                stage('Build') {
                    steps {
                echo "Build"
                sh 'mvn package -DskipTests'
                sh 'docker build -t="gurjeet151994/simple-project:latest" .'
                        }
                }
                stage('Deploy') {
                    steps {
                echo "Deploy"
                sh 'docker push gurjeet151994/simple-project:latest'
                    }
                }
                stage('Testing Environment') {
                    steps {
                        echo "hello"
                    }
                }
                stage('Staging') {
                    steps {
                        echo "hello"
                    }
                }
                stage('Production') {
                        when{
                            expression{
                                env.BRANCH_NAME=="master"
                            }
                        }
                        steps {
                            echo "hello"
                        }
                }
    }
}
