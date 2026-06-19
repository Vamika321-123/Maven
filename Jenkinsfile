node('built-in')
{
 stage('Continuous Download') 
 {
    git 'https://github.com/Vamika321-123/Maven.git'
}
 stage('Continuos Build')
 {
    sh 'mvn package'
}
stage('Continuous Deployment')
{
    deploy adapters: [tomcat9(alternativeDeploymentContext: '', credentialsId: '703010da-83fc-48d2-9d40-eb984d129d4c', path: '', url: 'http://3.27.138.85:8080')], contextPath: 'testapp', war: '**/*.war'
}
stage('Continuous Testing')
{  
    git 'https://github.com/Vamika321-123/FunctionalTesting.git'
}
stage('Continuos Delivery')
{
    deploy adapters: [tomcat9(alternativeDeploymentContext: '', credentialsId: '703010da-83fc-48d2-9d40-eb984d129d4c', path: '', url: 'http://3.106.203.76:8080')], contextPath: 'Prodapp', war: '**/*.war'
}
}
