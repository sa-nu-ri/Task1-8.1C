pipeline{
    agent any
    stages{
        stage('Build'){
            steps{
                echo "Buidling the code using 'Maven'..."
            }
        }
        stage('Unit and Integration Tests'){
            steps{
                echo "Performing unit tests using 'JUnit'..."
                echo "Performing integration tests using 'TestNG'..."
            }
            post{
                success{
                    mail to: "sm.sanuri.d@gmail.com"
                    subject: "Test Status Email: SUCCESS"
                    body: "Testing was successful!"
                }
                failure{
                    mail to: "sm.sanuri.d@gmail.com"
                    subject: "Test Status Email: FAILURE"
                    body: "Testing failed!"
                }
            }
        }
        stage('Code Analysis'){
            steps{
                echo "Analysing the code using 'SonarQube'..."
            }
        }
        stage('Security Scan'){
            steps{
                echo "Performing a security scan on the code using 'Snyk'..."
            }
            post{
                success{
                    mail to: "sm.sanuri.d@gmail.com"
                    subject: "Security Scan Status Email: SUCCESS"
                    body: "Security Scan was successful!"
                }
                failure{
                    mail to: "sm.sanuri.d@gmail.com"
                    subject: "Security Scan Status Email: FAILURE"
                    body: "Security Scan failed!"
                }
            }
        }
        stage('Deploy to Staging'){
            steps{
                echo "Deploying the application to 'AWS EC2' staging server..."
            }
        }
        stage('Integration Tests on Staging'){
            steps{
                echo "Performing integration tests using 'Selenium'..."
            }
        }
        stage('Deploy to Production'){
            steps{
                echo "Deploying the application to 'AWS EC2' production server..."
            }
        }
    }
}