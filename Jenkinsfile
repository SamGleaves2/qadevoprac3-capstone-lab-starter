pipeline {
    agent any
    environment {
        TF_VAR_gcp_project = "qwiklabs-gcp-02-03b4823ce4bb" // REPLACE WITH YOUR PROJECT ID FROM QWIKLABS
    }
    stages {
        stage("Configure Cluster") {
            steps {
                script {
                    dir('terraform') {
                        withCredentials([file(credentialsId: 'gcp_credentials', variable:'GCP_CREDENTIALS')]) {
                            sh '''
                                export GOOGLE_APPLICATION_CREDENTIALS=${GCP_CREDENTIALS}
                                terraform init
                                terraform apply -auto-approve
                            '''
                            // TODO: fill in the steps necessary to:
                            // - initialise terraform
                            // - scan the terraform files
                            // - provision the defined resources
                        }
                    }
                }
            }
        }
    }
    post {
        always {
            cleanWs()
        }
    }
}