ypipeline
{
    agent any
    stages
    {
        stage('continuous download') 
      {
        steps
        {
          git 'https://github.com/likith1728/maven-project.git'
        }
      }
      stage('continuous building')
      {
        steps
        {
          sh 'mvn package'  
        }
      }
      stage('continuous deployment') 
      {
         steps
        {
        deploy adapters: [tomcat8(credentialsId: '68e582c1-1356-4684-b477-799ca640c97c', path: '', url: 'http://172.31.6.245:8080')], contextPath: 'qaapp', war: '**/*.war'
        }
      }
      stage('continuous testing')
      { 
          steps
        {
          git 'https://github.com/likith1728/FunctionalTesting.git'
          sh 'java -jar /var/lib/jenkins/workspace/example3/testing.jar'
        }
      }
      stage('continuous delivery') 
      {
          steps
         {
          deploy adapters: [tomcat8(credentialsId: '68e582c1-1356-4684-b477-799ca640c97c', path: '', url: 'http://172.31.6.245:8080')], contextPath: 'qaapp', war: '**/*.war'
          mail bcc: '', body: 'test1', cc: 'likithreddy1728@gmail.com', from: '', replyTo: '', subject: 'test1', to: 'likithadithyadell.com'
         }
      }
    }
}
