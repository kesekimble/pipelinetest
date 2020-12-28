node{
        stage('SCM Checkout'){
                
                git 'https://github.com/javahometech/my-app'
                }
        stage('Compile Package'){
                def mvmhome = tool name: 'maven-3', type: 'maven'
                sh "${mvmhome}/bin/mvm package"
                
        }
}
