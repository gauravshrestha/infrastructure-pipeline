properties([pipelineTriggers([githubPush()])])
node('linux') {
    git url: 'https://github.com/gauravshrestha/infrastructure-pipeline.git', branch: 'master'
    stage('GetInstances') {
        sh "aws ec2 describe-instances --region us-east-1"
    }   
    stage ("CreateInstance") {
        sh "aws ec2 run-instances --image-id ami-09479453c5cde9639 --count 1 --instance-type t2.micro --key-name SEIS-665-KEY-Virginia --security-group-ids sg-0e77526f92d1bd5b8 --subnet-id subnet-035326bace6ba85c1 --region us-east-1"
    }
}
