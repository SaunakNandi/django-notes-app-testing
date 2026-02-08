@Library("Shared") _
pipeline {
    agent {label "saunak"}

    stages {
        stage('Hello') {
            steps {
                script {
                    hello()
                }
            }
        }
        stage('code') {
            steps {
                script {
                    clone("https://github.com/SaunakNandi/django-notes-app-testing.git","main")
                }
            }
        }
        stage('build') {
            steps {
                script {
                    docker_build('notes-app','latest','babluxyz')
                }
            }
        }
        stage('docker push') {
            steps {
                script {
                    docker_push("notes-app","dockerHubCred")
                }
            }
        }
        stage('deploy') {
            steps {
               script {
                   docker_compose()
               }
            }
        }
    }
}

// @Library('Shared')_
// pipeline{
//     agent { label 'dev-server'}
    
//     stages{
//         stage("Code clone"){
//             steps{
//                 sh "whoami"
//             clone("https://github.com/LondheShubham153/django-notes-app.git","main")
//             }
//         }
//         stage("Code Build"){
//             steps{
//             dockerbuild("notes-app","latest")
//             }
//         }
//         stage("Push to DockerHub"){
//             steps{
//                 dockerpush("dockerHubCreds","notes-app","latest")
//             }
//         }
//         stage("Deploy"){
//             steps{
//                 deploy()
//             }
//         }
        
//     }
// }
