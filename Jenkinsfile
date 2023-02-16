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
                   -Dsonar.login=sqp_c731886bc857f9559b31cd762bfec53b1982c4d8
           '''
            }
        }

    }
}