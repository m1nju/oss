node{
    def app
    stage('Clone repository'){
        git 'https://github.com/m1nju/oss.git'
    }
    stage('Build image'){
        app = docker.build("sarah1153/prbasedtest")
    }
    stage('Push image'){
        docker..withRegistry('https://registry.hub.docker.com', 'dockerhub') {
        app.push("${env.BUILD_NUMBER}")
        app.push("latest")
        }
    }
}
