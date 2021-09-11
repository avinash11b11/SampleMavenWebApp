pipeline{
    agent any
    stages{
        stage('Clean'){
            steps{
                cleanWs()
                
                bat '''
                   set MAVEN_HOME=E:/Work Related/Softwares/apache-maven-3.6.3-bin/apache-maven-3.6.3/
                    
                '''
                
                echo "Java Home : ${env.JAVA_HOME}"
                echo "Maven Home : ${env.MAVEN_HOME}"
                echo "Running ${env.BUILD_ID} on ${env.JENKINS_URL}"
                
                
            }
        }
        stage('Checkout'){
            steps{
                  checkout poll: false, scm: [$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'github_pat', url: 'https://github.com/avinash11b11/SampleMavenWebApp']]]
            }
        }
        stage('Build'){
            steps{
                   bat '''
                       mvn --version
                       '''
            }
        }
    }
}
