pipeline {
    agent {
        label {
            label "built-in"
            customWorkspace "/mnt/hoow"
        }
    }

    stages {
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
    }
}
