pipeline {
    agent any
    stages {
        stage ('Build Package') {
            steps {
                /*For windows machine */
                bat 'mvn clean package'

                /*For Mac & Linux machine */
                // sh 'mvn clean package'
            }
        }

        stage ('Archive war file') {
            post{
                success{
                    echo 'Now Archiving ...'

                    archiveArtifacts artifacts : '**/*.war'
                }
            }
        }
    }
}
