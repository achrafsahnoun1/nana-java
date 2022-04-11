def gv
pipeline {
    agent any
    tools{
        maven 'maven-3.8'
    }
 
    stages {
        stage("build app") {
           
            steps {
                script{
                    
                    gv.buildJar()
                }
            }
        }
        stage("Building the image") {
            
            steps {
                script {
                    gv.buildImage()
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
