pipeline
{
    agnt any
        stages
    {
        stage('Build')
        {
            steos
            {
                sh 'mvn clean install' echo 'Build Stage Successful'
            }
        }

        stage('Test')
        {
            steps
            {
                sh 'mvn test' echo 'Test Stage Successful' post
                {
                    always
                    {
                        junit 'target/surefire-reports/*.xml'
                    }
                }
            }
        }
        stage('Deploy')
        {
            steps
            {
                sh 'mvn deploy' echo 'Deployment Successful'
            }
        }
    }
    post
    {
        failure
        {
            echo 'pipeline failed'
        }
    }
}
