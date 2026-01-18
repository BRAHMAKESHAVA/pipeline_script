pipeline {
    agent none

    stages {

        stage('Non-Parallel Stage') {
            agent {
                label "Master"
            }
            steps {
                echo 'This stage will be executed first on Built-In Node'
            }
        }

        stage('Run Tests') {
            parallel {

                stage('Test On Windows Node') {
                    agent {
                        label "Windows_Node1"
                    }
                    steps {
                        echo "Task1 on Windows_Node1 (Slave)"
                    }
                }

                stage('Test On Built-In Node') {
                    agent {
                        label "Master"
                    }
                    steps {
                        echo "Task1 on Built-In Node (Master)"
                    }
                }
            }
        }
    }
}
