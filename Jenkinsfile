properties([pipelineTriggers([githubPush()])])

pipeline {
    agent {
        docker {
            image 'hashicorp/terraform'
            args '--entrypoint='
        }
    }

    environment {
	AWS_ACCESS_KEY_ID	= credentials('AKIAXEQG34BCFOFGTSH3')
        AWS_SECRET_ACCESS_KEY	= credentials('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')
	TF_IN_AUTOMATION	= '1'
    }

    stages {
        stage('Init Terraform directory') {
            steps {
                sh 'terraform init'
            }
        }
        stage('Plan terraform code') {
            steps {
                sh 'terraform plan'
            }
        }
        stage('Apply terraform code') {
            steps {
                sh 'terraform apply -auto-approve'
            }
        }
    }
}
