
/*
    Building and Deploying WAR on Jenkins-Master 
*/
pipeline {
    agent {
        label {
            label "built-in"
            customWorkspace "/mnt/hoow"
        }
    }

    stages {
        stage ("stage-1") {
            steps {
                sh "rm -rf *"
                sh "git clone https://github.com/Darzzzz/q1q2q3-jenkinsfile-docker.git -b 2023Q1"

                dir ("/mnt/hoow/q1q2q3-jenkinsfile-docker") {
                    sh "pwd"
                    sh "ls -ltr"
                    sh "cat index.html"
                    sh "chmod -R 644 index.html"
                    sh "ls -ltr"
                    
                    // Check if the container exists before attempting to stop and remove it
                    script {
                        def containerExists = sh(script: 'docker ps -a | grep -q "as1"', returnStatus: true) == 0
                        if (containerExists) {
                            sh "docker kill as1"
                            sh "docker rm as1"
                        } else {
                            echo "Container 'as1' does not exist."
                        }
                    }
                    
                    sh "docker run -itdp 8090:80 --name as1 httpd"
                    sh "docker cp index.html as1:/usr/local/apache2/htdocs"
                }
            }
        }

        stage ("stage-2") {
            steps {

                dir ("/mnt/aoow") {
                    sh "rm -rf *"
                    sh "git clone https://github.com/Darzzzz/q1q2q3-jenkinsfile-docker.git -b 2023Q2"
                        
                        dir ("/mnt/aoow/q1q2q3-jenkinsfile-docker") {
                            sh "pwd"
                            sh "ls -ltr"
                            sh "cat index.html"
                            sh "chmod -R 644 index.html"
                            sh "ls -ltr"
                            
                            // Check if the container exists before attempting to stop and remove it
                            script {
                                def containerExists = sh(script: 'docker ps -a | grep -q "as2"', returnStatus: true) == 0
                                if (containerExists) {
                                    sh "docker stop as2"
                                    sh "docker rm as2"
                                } else {
                                    echo "Container 'as2' does not exist."
                                }
                            }
                            
                            sh "docker run -itdp 8001:80 --name as2 httpd"
                            sh "docker cp index.html as2:/usr/local/apache2/htdocs"
                        }
                }
            }
        }

        stage ("stage-3") {
            steps {

                dir ("/mnt/woow") {
                    sh "rm -rf *"
                    sh "git clone https://github.com/Darzzzz/q1q2q3-jenkinsfile-docker.git -b 2023Q3"
                        
                        dir ("/mnt/woow/q1q2q3-jenkinsfile-docker") {
                            sh "pwd"
                            sh "ls -ltr"
                            sh "cat index.html"
                            sh "chmod -R 644 index.html"
                            sh "ls -ltr"
                            
                            // Check if the container exists before attempting to stop and remove it
                            script {
                                def containerExists = sh(script: 'docker ps -a | grep -q "as3"', returnStatus: true) == 0
                                if (containerExists) {
                                    sh "docker stop as3"
                                    sh "docker rm as3"
                                } else {
                                    echo "Container 'as3' does not exist."
                                }
                            }
                            
                            sh "docker run -itdp 8002:80 --name as3 httpd"
                            sh "docker cp index.html as3:/usr/local/apache2/htdocs"
                        }
                }
            }
        }

        stage ("stage-4") {
            steps {

                dir ("/mnt/xoow") {
                    sh "rm -rf *"
                    sh "git clone https://github.com/Darzzzz/q1q2q3-jenkinsfile-docker.git -b 2023Q5"
                        
                        dir ("/mnt/xoow/q1q2q3-jenkinsfile-docker") {
                            sh "pwd"
                            sh "ls -ltr"
                            sh "cat index.html"
                            sh "chmod -R 644 index.html"
                            sh "ls -ltr"
                            
                            // Check if the container exists before attempting to stop and remove it
                            script {
                                def containerExists = sh(script: 'docker ps -a | grep -q "as4"', returnStatus: true) == 0
                                if (containerExists) {
                                    sh "docker stop as4"
                                    sh "docker rm as4"
                                } else {
                                    echo "Container 'as4' does not exist."
                                }
                            }
                            
                            sh "docker run -itdp 90:80 --name as4 httpd"
                            sh "docker cp index.html as4:/usr/local/apache2/htdocs"
                        }
                }
            }
        }
    }
}
