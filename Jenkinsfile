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
                // sh "git clone https://github.com/Darzzzz/pipe.git"
                
                // dir("/mnt/xyz") {
                    sh "pwd"
                    sh "ls -ltr"
                    sh "cat index.html"
                    // sh "chmod -R 644 index.html"
                    sh "cp index.html /var/www/html"
                // }
            }
        }
    }
}
