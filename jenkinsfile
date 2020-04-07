pipeline{
    tools{
        jdk 'myjava'
        maven 'mymaven'
    }
    agent none
    stages{
//        stage('checkout'){
//            agent any
//            steps{
//                git 'https://github.com/devops-trainer/game-of-life.git'
//            }//step
//        }//stage checkout
        stage('Compile'){
            agent any
            steps{
                sh 'mvn compile'
            }
        }
                stage('Test'){
            agent any
            steps{
                sh 'mvn test'
            }
            post{
                always{
                    junit 'gameoflife-web/target/surefire-reports/*.xml'
                }
            }
        }
                stage('Package'){
            agent any
            steps{
                sh 'mvn package'
            }
        }
    }
}
