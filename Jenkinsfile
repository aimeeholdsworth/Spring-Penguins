pipeline{
        agent any
        stages{
            stage('Build'){
                steps{
                    sh "mvn clean package"
                }
            }
           stage('Test') { 
            steps {
                sh 'mvn test' 
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml' 
                }
            }
        }
            stage('Deploy'){
                steps{
                    java -jar 'target/spring-penguins-0.0.1-SNAPSHOT.jar'
                }
            }
        }
}
