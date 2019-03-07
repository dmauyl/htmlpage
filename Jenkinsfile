node {

stage('Clone Repository')
{
checkout scm
}

stage('Show me the files'){
sh "ls -l"
}

stage('Build docker image'){

sh "docker build -t michaelodongo:latest ."
}

stage('Docker login to hub and push the image'){

sh "docker login -u 'mikodongo' -p 'Mqxzygi4%iaj!' "
sh "docker tag michaelodongo:latest mikodongo/devopsexams:latest"
sh "docker push mikodongo/devopsexams:latest"
}

stage('Apply changes to the environment') {
sh "ls -l"
}
stage("docker run image")
{
sh "docker run --name jenkins-docker -p 2989:2989 -v /var/run/docker.sock:/var/run/docker.sock 
mikodongo/jenkins-docker"
}

}
