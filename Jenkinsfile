
















pipeline
{
    agent any
    stages
    {
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
          mail bcc: '', body: 'test1', cc: 'roshni.vijaykumar6@gmail.com', from: '', replyTo: '', subject: 'test1', to: 'likithreddy1728@gmail.com'
         }
      }
    }
}





































