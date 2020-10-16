pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                // Get some code from a GitHub repository
               // git 'https://github.com/pgottam/spring-petclinic-api-gateway.git'

                // Run Maven on a Unix agent.
                //sh "/Users/praveeng/Downloads/tkg/apache-maven-3.6.3/bin/mvn clean package"
                sh ' echo test'
                // To run Maven on a Windows agent, use
                // bat "mvn -Dmaven.test.failure.ignore=true clean package"
            }    
        }
        stage('kp') {
            steps {
                
                // Run Maven on a Unix agent.
                sh 'rm -f /Users/praveeng/Downloads/tbs/out.txt'
                sh "/usr/local/bin/kp image list"
                
               // sh '/usr/local/bin/kp image create petclinic --tag harbor.pgottam-demo.live/devregistry/api-gateway --git https://github.com/pgottam/spring-petclinic-api-gateway.git --git-revision master'
                sh '/usr/local/bin/kp image list'
                sh '/usr/local/bin/kp build list petclinic  | grep SUCCESS | tail -1 > /Users/praveeng/Downloads/tbs/out.txt'
                sh '/Users/praveeng/Downloads/tbs/loop.sh'
                sh 'echo $BUILD_NUMBER'
               // sh '/usr/bin/expect -c "set timeout 180;spawn /usr/local/bin/kp secret create clinic --registry harbor.pgottam-demo.live --registry-user admin;expect \\\"registry password: \\\";send \"admin\r\";expect eof"'
                //sh '/usr/bin/expect -c "${expectCmd}"'
                
                // To run Maven on a Windows agent, use
                // bat "mvn -Dmaven.test.failure.ignore=true clean package"
            }
        }
    }
}

