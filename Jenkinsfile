#!groovy
@library('jenkinslib') _

def tools = new org.devops.tools()

pipeline{
    agent any

    options{ 
        timestamps()
        disableConcurrentBuilds()
    }

    stages{
        stage('Build'){
            steps{
                echo 'Building the project'
            }
        }
        stage('Test'){
            steps{
                echo 'Testing the project'
            }
        }
        stage('Deploy'){
            steps{
                echo 'Deploying the project'
                script{
                    tools.printMsg('this is my library')
                }
            }
        }
    }

    post{
        always{
            echo 'This will always run'
        }
        success{
            echo 'This will run only if the pipeline is successful'
            script{
                currentBuild.description = 'BUILD SUCCESS'
            }
        }
        failure{
            echo 'This will run only if the pipeline is failed'
            script{
                currentBuild.description = 'BUILD FAILURE'
            }
        }
        unstable{
            echo 'This will run only if the pipeline is unstable'
        }
        changed{
            echo 'This will run only if the pipeline status is changed'
        }
    }
}
