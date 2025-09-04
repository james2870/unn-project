node {
     stage('Clone repository') {
         checkout scm
     }
     stage('Build image') {
         app = docker.build("unn-project/mynginx4")
         
     }
     stage('Push image') {
         docker.withRegistry('https://ec2-43-203-193-163.ap-northeast-2.compute.amazonaws.com/', 'harbor-reg') {
             app.push("${env.BUILD_NUMBER}")
             app.push("latest")
         }
     }
}
