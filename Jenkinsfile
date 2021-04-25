node('master')
{
stage('Continuous Download') 
{
git 'https://github.com/intelliqittrainings/maven.git'
}
stage('Continuous Build')
{
sh 'mvn package'
}
stage('Continuous Deployment')
{
sh 'scp /home/ubuntu/.jenkins/workspace/ScriptedPipeline/webapp/target/webapp.war ubuntu@172.31.41.230:/var/lib/tomcat8/webapps/qaapp.war'
}
stage('Continuous Testing')
{
git 'https://github.com/selenium-saikrishna/FunctionalTesting.git'
sh 'java -jar /home/ubuntu/.jenkins/workspace/ScriptedPipeline/testing.jar'
}
stage ('Continuous Delivery')
{
sh 'scp /home/ubuntu/.jenkins/workspace/ScriptedPipeline/webapp/target/webapp.war ubuntu@172.31.36.67:/var/lib/tomcat8/webapps/prodapp.war'
}
} 
