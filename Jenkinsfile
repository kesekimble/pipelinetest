properties([parameters([choice(choices: ['master', 'future1', 'future2'], description: 'Select Branch to Build From', name: 'branch')])])
node{
        stage('SCM Checkout'){
                
                git 'https://github.com/javahometech/my-app', branch: "${params.branch}"
                }
        stage('Compile Package'){
                def mvmhome = tool name: 'maven-3', type: 'maven'
                sh "${mvmhome}/bin/mvn package"
                
        }
        stage('Deploy to Apache'){
                sh 'cp /apps/opt/jenkins_home/workspace/pipeline2-maven-git/target/myweb-0.0.12.war /apps/opt/apache/apache-tomcat-9.0.0.M10/webapps'
        }
}
