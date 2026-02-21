pipeline {
    agent any
//Нарочно не съм сложил when защото според мен не е добра практика да има такава условна
//логика в Jenkinsfile-а. Тя трябва да се направи от билда, който го извиква.
// и ако трябва  билда да се пуска на определен бранч, то pipelin-а трябва да е 
// мулти-branch pipeline, който да се пуска само на този бранч. 
    stages {

        stage('Restore dependencies') {
            steps {
                bat 'dotnet restore'
            }
        }

        stage('Build') {
            steps {
                bat 'dotnet build --no-restore'
            }
        }

        stage('Run tests') {
            steps {
                bat 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}
