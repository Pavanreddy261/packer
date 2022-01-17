pipeline {
    agent any
    stages {
        stage('Dockerized') {
            agent {
                dockerfile {
                    reuseNode true
                    dir 'docker'
                    args '-ti --entrypoint=/bin/bash'
                    args  '-v $PWD:/packer/'
                }
            }
        stages {
                    stage('Init Packer NonProd') {
                        steps{
                                sh 'packer --version'
                            }
                    }
                    stage('Validate NonProd') {
                        when {
                            not {
                                branch 'main'
                            }
                        }
                        steps {
                                withAWS(credentials:'skx-ecomm-nonprod') {
                                    sh 'packer validate ./packer/packer.json'
                                }
                            }
                    }
                    stage('Build NonProd') {
                        when {
                            not {
                                branch 'main'
                            }
                        }
                        steps {
                                withAWS(credentials:'skx-ecomm-nonprod') {
                                    sh 'packer build ./packer/packer.json'
                                }
                            }
                    }
                }
        }
    }
    
}
