pipeline {
    agent any
    triggers {
        githubPush()
    }
    stages {
        stage('Restore packages'){
           steps{
               sh 'dotnet restore HelloWorld.sln'
            }
         }
        stage('Clean'){
           steps{
               sh 'dotnet clean HelloWorld.sln --configuration Release'
            }
         }
        stage('Build'){
           steps{
               sh 'dotnet build HelloWorld.sln --configuration Release --no-restore'
            }
         }
         stage('Run'){
           steps{
               sh 'dotnet run HelloWorld.sln --configuration Release --no-restore'
            }
         }
         
    }
}