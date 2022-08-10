pipeline {
    agent none

    environment {
        ENV_DOCKER = credentials('dockerhub')
        DOCKERIMAGE = "Springboot/springboot"
        EKS_CLUSTER_NAME = "cluster"
    }
    stages {
        stage('build') {
            agent {
                docker { image 'openjdk:11-jdk' }
            }
            steps {
                sh 'chmod +x gradlew && ./gradlew build jacocoTestReport'
            }
        }
        // stage('sonarqube') {
        //     agent {
        //         docker { image 'sonarsource/sonar-scanner-cli'} 
        //     }
        //     steps {
        //         sh 'echo scanning!'
        //     }
        // }
        // stage('docker build') {
        //     steps {
        //         // git 'https://github.com/salyx21/spring-boot-practice.git'

        //         sh 'echo docker build'
        //     }
        // }
        // stage('docker push') {
        //     steps {
        //         // sh 'docker push salyx21/springboot:${env.BUILD_NUMBER}'
        //         sh 'echo docker push!'
        //         }
        //     }
        // stage('Deploy App') {
        //     steps {
        //         sh 'echo deploy to kubernetes'               
        //     }
        // }
    }
}
