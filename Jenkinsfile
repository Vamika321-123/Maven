pipeline
{
    agent any
    stages
    {
        stage('Download')
        {
            steps
            {
                git 'https://github.com/Vamika321-123/Maven.git'
            }
        }
        stage('Build')
        {
            steps
            {
                sh 'mvn package'
            }
        }
        stage('Deployment')
        {
            steps
            {   
                deploy adapters: [tomcat9(alternativeDeploymentContext: '', credentialsId: '703010da-83fc-48d2-9d40-eb984d129d4c', path: '', url: 'http://15.135.112.103:8080')], contextPath: 'mytestapp', war: '**/*.war'
            }
        }
        stage('Testing')
        {
            steps
            {
                git 'https://github.com/Vamika321-123/FunctionalTesting.git'
                sh 'java -jar /var/lib/jenkins/workspace/Declarative1/testing.jar'
            }
        }
        stage('Delivery')
        {
            steps
            {
                deploy adapters: [tomcat9(alternativeDeploymentContext: '', credentialsId: '703010da-83fc-48d2-9d40-eb984d129d4c', path: '', url: 'http://3.27.148.187:8080')], contextPath: 'myprodapp', war: '**/*.war'
            }
        }
    }
}
