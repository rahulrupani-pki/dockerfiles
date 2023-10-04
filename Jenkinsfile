
pipeline {
    agent {
        ecs {
            inheritFrom 'build-example-spot'
        }
    }
    stages {
        stage('Test Build') {
            parallel {
                stage {
                    steps {
                        script {
                            dir('apache'){
                                sh "echo Apache Build"
                                sh '''
                                    docker build --tag name:apache . 
                                '''
                            }
                        }
                        sh 'sleep 120'
                        sh 'echo sleep is done'
                    }
                }
                stage {
                    steps{
                        script {
                            dir('apache2'){
                                sh "echo Apache2 Build"
                                sh '''
                                    docker build --tag name:apache2  . 
                                '''
                            }
                        }
                        sh 'sleep 120'
                        sh 'echo sleep is done'
                    }
                }
                stage {
                    steps{
                        script {
                            dir('centos'){
                                sh "echo Centos Build"
                                sh '''
                                    docker build --tag name:centos . 
                                '''
                            }
                        }
                        sh 'sleep 120'
                        sh 'echo sleep is done'
                    }
                }
                stage {
                    steps{
                        script {
                            dir('centos2'){
                                sh "echo Centos2 Build"
                                sh '''
                                    docker build --tag name:centos2 . 
                                '''
                            }
                        }
                        sh 'sleep 120'
                        sh 'echo sleep is done'
                    }
                }
                stage {
                    steps{
                        script {
                            dir('Python'){
                                sh "echo Python Build"
                                sh '''
                                    docker build --tag name:python . 
                                '''
                            }
                        }
                        sh 'sleep 120'
                        sh 'echo sleep is done'
                    }
                }
                stage {
                    steps{
                        script {
                            dir('Python2'){
                                sh "echo Python2 Build"
                                sh '''
                                    docker build --tag name:python . 
                                '''
                            }
                        }
                        sh 'sleep 120'
                        sh 'echo sleep is done'
                    }
                }
                stage {
                    steps{
                        script {
                            dir('Ubuntu'){
                                sh "echo Ubuntu Build"
                                sh '''
                                    docker build --tag name:ubuntu . 
                                '''
                            }
                        }
                        sh 'sleep 120'
                        sh 'echo sleep is done'
                    }
                }
                stage {
                    steps{
                        script {
                            dir('Ubuntu2'){
                                sh "echo Ubuntu2 Build"
                                sh '''
                                    docker build --tag name:ubuntu2 . 
                                '''
                            }
                        }
                        sh 'sleep 120'
                        sh 'echo sleep is done'
                    }
                }
            }
        }
    }
    post {
        always {         
            /* clean up our workspace */
            deleteDir()
            /* clean up tmp directory */
            dir("${workspace}@tmp") {
                deleteDir()
            }
            /* clean up script directory */
            dir("${workspace}@script") {
                deleteDir()
            }
        }
    }
}
