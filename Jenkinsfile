pipeline{
    agent any
    stages{
        stage ('checkout the code from SCM'){
            steps{
                echo 'checkout the code'
            }
        }
        stage ('Build the project'){
            steps{
                echo 'building the project'
                sh 'mvn clean install -DskipTests'
            }
        }
        stage('Sonarqube'){
            steps{
                echo 'Sonar Codequality'
                sh '''
                mvn clean verify sonar:sonar \
                   -Dsonar.projectKey=Mobilestore \
                   -Dsonar.host.url=http://20.151.88.32:9000 \
                   -Dsonar.login=sqp_691ca2b205f75ffa2df3d91fd73814b9578204f2
           '''
            }
        }

    }
}