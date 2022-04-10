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
            input{
                message "select env"
                ok "Done"
                parameters{
                    choice(name: 'ENV', choices: ['dev','prod'],description: '')

                }
            }
            steps {
                script {
                    echo "testing the app in ${ENV}"
                }
            }
        }
        stage("deploy ") {
            steps {
                script {
                    gv = load "script.groovy"
                    gv.deployApp()
                }
            }
        }
       
    }   
}
