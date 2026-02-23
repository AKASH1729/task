@Library('Shared') _
pipeline {
    agent { label 'Node' }

  

    parameters {
        string(name: 'FRONTEND_DOCKER_TAG', defaultValue: '', description: 'Frontend Docker image tag')
        string(name: 'BACKEND_DOCKER_TAG', defaultValue: '', description: 'Backend Docker image tag')
    }

    stages {

        stage("Validate Parameters") {
            steps {
                script {
                    if (params.FRONTEND_DOCKER_TAG == '' || params.BACKEND_DOCKER_TAG == '') {
                        error("FRONTEND_DOCKER_TAG and BACKEND_DOCKER_TAG must be provided.")
                    }
                }
            }
        }

        stage("Workspace Cleanup") {
            steps {
                cleanWs()
            }
        }

        stage("Git: Code Checkout") {
            steps {
                script {
                    code_checkout(
                        "https://github.com/AKASH1729/task.git",
                        "main"
                    )
                }
            }
        }

      

      


        stage("Docker: Build Images") {
            steps {
                script {
                    dir('backend') {
                        docker_build(
                            "cron-backend",
                            "${params.BACKEND_DOCKER_TAG}",
                            "akas11729"
                        )
                    }

                    dir('frontend') {
                        docker_build(
                            "cron-frontend",
                            "${params.FRONTEND_DOCKER_TAG}",
                            "akas11729"
                        )
                    }
                }
            }
        }

        stage("Docker: Push Images") {
            steps {
                script {
                    docker_push("cron-backend", "${params.BACKEND_DOCKER_TAG}", "akas11729")
                    docker_push("cron-frontend", "${params.FRONTEND_DOCKER_TAG}", "akas11729")
                }
            }
        }
    }

    post {
        success {
            archiveArtifacts artifacts: '*.xml', followSymlinks: false

            build job: "Cron-CD",
                parameters: [
                    string(name: 'FRONTEND_DOCKER_TAG', value: "${params.FRONTEND_DOCKER_TAG}"),
                    string(name: 'BACKEND_DOCKER_TAG', value: "${params.BACKEND_DOCKER_TAG}")
                ]
        }
    }
}