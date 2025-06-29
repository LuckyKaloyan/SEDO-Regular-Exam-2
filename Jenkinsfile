pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm 
            }
        }
        stage('Restore the project') {
            when { branch 'main' }
            steps {
                bat 'dotnet restore HouseRentingSystem.sln'
            }
        }

        stage('Build the project up') {
            when { branch 'main' }
            steps {
                bat 'dotnet build HouseRentingSystem.sln'
            }
        }

        stage('Test the project') {
            when { branch 'main' }
            steps {
                bat 'dotnet test HouseRentingSystem.sln --no-build --verbosity normal'
            }
        }
    }
}
