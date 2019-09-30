pipeline{
    agent any
        stages{
   
           stage('Build'){
               steps{
git url: 'https://github.com/mythribhay/hello-world-war.git'
             }
        }
       
        stage('Maven package'){
            steps{
       
            sh '/opt/maven/bin/mvn clean package'
        }
        }
        stage('Deploy the war file to tomcat container'){
            steps{
                deploy adapters: [tomcat9(credentialsId: '8f5c7a7d-2a22-4a3b-a1df-98f43912b108', path: '', url: 'http://3.19.185.39:8888/')], contextPath: 'Hello-world-warr', war: '**/*.war'
            }
        }
    }
}
