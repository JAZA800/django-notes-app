@Library('Shared') _
pipeline{
    agent { label 'wick'}
    
    stages{
        stage("Code clone"){
            steps{
            clone("https://github.com/LondheShubham153/django-notes-app.git","main")
            }
        }
        stage("Code Build"){
            steps{
            docker_build("notes-app","latest","jaza1242")
            }
        }
        stage("Push to DockerHub"){
            steps{
                docker_push("notes-app","latest","jaza1242")
            }
        }
        stage("Deploy"){
            steps{
                echo "this is deploying the code"
                sh "docker compose up -d"
            }
        }
        
    }
}
