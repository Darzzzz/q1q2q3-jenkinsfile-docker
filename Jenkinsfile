pipeline{
    agent {
        label {
            label "built-in"
            customWorkspace "/mnt/xyz"
        }
    }

    stages {
        stage ("stage-1") {
            steps {
                sh "rm -rf *"
                sh "git clone https://github.com/Darzzzz/pipe.git"

                dir("/mnt/xyz/pipe") {
                    sh "pwd"
                    sh "ls -ltr"
                    sh "cat index.html"
                    // sh "chmod -R 644 index.html"
                    sh "cp index.html /var/www/html"
                }
            }
        }

        stage ("stage-2") {
            steps {
                sh "sleep 10"

                dir ("/mnt/zyx") {
                    sh "rm -rf *"
                    sh "git clone https://github.com/Darzzzz/pipe.git -b 2023Q1"

                    dir("/mnt/zyx/pipe") {
                        sh "pwd"
                        sh "ls -ltr"
                        sh "cat index.html"
                        // sh "chmod -R 644 index.html"
                        sh "cp index.html /var/www/html"
                    }
                }
            }
        }
    }
}
