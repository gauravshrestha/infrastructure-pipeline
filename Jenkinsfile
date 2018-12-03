properties([pipelineTriggers([githubPush()])])
node('linux') {
    git url: 'https://github.com/gauravshrestha/infrastructure-pipeline.git', branch: 'master'
    stage('Unit Tests') {
        sh "ant -f test.xml -v"
        junit 'reports/result.xml'
    }   
}
