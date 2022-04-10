pipeline {
    agent any
    parameters {
        choice(name: 'VERSION', choices: ['1.0','1.1'],description: '')
    }
    stages {
        stage("build") {
            when {
                expression{
                    params.VERSION == '1.0'
                }
            }
            steps {
                
                echo "building the app"

            }
        }
        stage("test") {
            steps {
                script {
                    echo "testing the app"
                }
            }
        }
        stage("deploy ") {
            steps {
                script {
                    echo "deploying the app"
                }
            }
        }
        stage("deploy") {
            steps {
                script {
                    echo "deploying"
                    //gv.deployApp()
                }
            }
        }
    }   
}
