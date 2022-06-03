pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
              echo "Cloning the source code........" 
            }
        }
        stage('compile') {
            steps {
               echo "Compiling the application........" 
            }
        }
        stage('build') {
            steps {
               echo "Building the application........"
            }
        }
        stage('test') {
            steps {
              echo "Testing the application........" 
            }
        }
        stage('package') {
            steps {
               echo "Packaging the application........"
            }
        }
        stage('deploy') {
            steps {
               echo "Deploying the application........"
            }
        }
    }
}
Running a shell script in the pipeline
pipeline {
    agent any
    stages {
        stage('Hello World') {
            steps {
                echo "Hello World"
            }
        }
        stage('Run shell commands') {
            steps {
               sh '''
                 #!/bin/bash
                 echo "hello world" 
                 ls -la
                 cat /etc/*release
                ''' 
            }
        }
    }
}
pipeline {
    agent any
    stages {
        stage('Hello World') {
            steps {
                echo "Hello World"
            }
        }
        stage('Run shell commands') {
            steps {
               sh '''
                #! /bin/bash

                # Uninstall old versions
                sudo yum remove docker \\
                                docker-client \\
                                docker-client-latest \\
                                docker-common \\
                                docker-latest \\
                                docker-latest-logrotate \\
                                docker-logrotate \\
                                docker-engine

                # this will download the script package to install docker
                curl -fsSL https://get.docker.com -o get-docker.sh
                # this will install the package
                sudo sh get-docker.sh

                sudo systemctl enable docker
                sudo systemctl start docker
                sudo docker run hello-world
                sudo docker run docker/whalesay cowsay hello-world!
                ''' 
            }
        }
    }
}
