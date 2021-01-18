properties([pipelineTriggers([githubPush()])])

pipeline {
    agent { 
      docker {
        image 'hashicorp/terraform'
        args  '--entrypoint='
      }
    }
    
    stages('TF init) {
    steps {
       sh 'terraform init'
    }
    }
    stages('TF plan'){
    steps {
       sh 'terraform plan'
    }
    }
    stages('TF apply'){
    steps{
       sh 'terraform apply -auto-approve'
    }
    }
}
