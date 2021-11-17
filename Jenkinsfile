pipeline{
    agent{
        label 'Agent'
    }
    options {
        buildDiscarder (logRotator(numToKeepStr: '5'))
    }
    stages{
        stage('Scan'){
            environment{
                projectKey = "Eladio-Fase-III"
                url = "https://serincprd01.cfbhd.com/sonarqube/"
                token = "7655c49a166dde372467eacd8f0ea2bccdf52bd9"
            }
            steps {
                withSonarQubeEnv(installationName: 'sonarqube-premisa'){
                    bat "dotnet sonarscanner begin k:${projectKey} /d:sonar.host.url=${url} /d:sonar.login=${token}"
                }
            }
        }
    }
}