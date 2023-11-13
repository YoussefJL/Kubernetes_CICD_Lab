pipeline{
    agent any
    stages{

        stage("getting code") {
            steps {
                git url: 'https://github.com/YoussefJL/Kubernetes_CICD_Lab.git', branch: 'main',
                credentialsId: 'github-credentials' //jenkins-github-creds
                sh "ls -ltr"
            }
        }

	stage('Deploy the application on kubernetes cluster')
                {
              steps{
                  script{
                    withKubeConfig(caCertificate: '', clusterName: '', contextName: '', credentialsId: 'k8s', namespace: '', restrictKubeConfigAccess: false, serverUrl: '') {
			            sh 'kubectl delete -f .'
                        sh 'kubectl apply -f .'
                    }
                    }
                  }
        }
    }
}