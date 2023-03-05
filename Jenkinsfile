pipeline {
    agent any 
    parameters {
  booleanParam description: 'true value', name: 'true'
}

    stages{
        stage('BUILD') {
            steps{
                 sh '''
                    sleep 5
                    echo "This is a BUILD stage"
                '''
            }
        }

        stage('TEST') {
            parallel {

                stage('TEST ON LINUX MACHINE') {
                    steps {
                        sh '''
                            sleep 6
                            echo "This is a TEST on LINUX"
                            exit 1
                        '''
                    }
                }

                stage('TEST ON WINDOWS MACHINE') {
                    steps {
                        sh '''
                            sleep 6
                            echo "This is a TEST on WINDOWS"
                        '''
                    }
                }


        stage('DEPLOY') {
            steps{
                sh '''
                    sleep 5
                    echo "This is a DEPLOY stage"
                    exit 0
                '''
            }
        }
    }
}
