pipeline{
    agent any
    stages{

        stage('Checkout from Git') {
            steps {
                git branch: 'main', url: 'https://github.com/YoussefJL/Kubernetes_CICD_Lab.git'
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