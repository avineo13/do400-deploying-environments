pipeline {

    agent {

        node {
            label 'maven'
        }

    }

    stages {

        stage('Tests') {

            steps {

                sh './mvnw clean test'

            }
        }

        stage('Package') {

            steps {

                sh '''
                    ./mvnw package -DskipTests 
                    -D quarkus.package.type=uber-jar
                '''

                archiveArtifacts 'target/*.jar'

            }
        }

    }
}