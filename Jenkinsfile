pipeline {
    agent any
      environment {
        K8S_CLUSTER_ID = 'jpe1-caas1-dev1'
        K8S_NAMESPACE = "${env.JOB_NAME.split('/')[3]}"
    }
    stages {
        stage('scm') {
            steps {
                git branch: 'main', url: 'https://github.com/ArnabMajumder009/spring-crud-k8s.git'
            }
        }
        
         stage('k8s') {
            steps {
                
                script{
                    //docker login 'registry-jpe1.r-local.net' -u 'Arnab_Majumder' -p 'SnjfhCdrQVm3FcPl4K4FuoQConXbGebl'
                   // docker pull registry-jpe1.r-local.net/cpd-support-my-first-ns/mysql:1.0
                    
                   // spring-mysql-CRUD Application deployment
                    
                   cpd.kubectl('apply -f spring.yaml')
                   cpd.kubectl('apply -f mysql-db.yaml')
                   cpd.kubectl('apply -f mysql-config.yaml')
                   cpd.kubectl('apply -f mysql-secretUpdate Jenkinsfile.yaml')
                    
                   
               }
                
            }
        }
        
        
    }
}
