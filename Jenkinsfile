pipeline {
    agent any

    tools {
        // Install the Maven version configured as "M3" and add it to the path.
       maven "maven3.6.3"
    }

    stages {
        stage('Build&Deploy') {
            steps {
                // Get some code from a GitHub repository
                git 'https://github.com/narendra0802/mavenprojects'

                // Run Maven on a Unix agent.
                sh "mvn package"
                sh "cp target/JenkinsWar.war /var/lib/tomcat8/webapps/"

                // To run Maven on a Windows agent, use
                // bat "mvn -Dmaven.test.failure.ignore=true clean package"
            }
        }
    }
}
