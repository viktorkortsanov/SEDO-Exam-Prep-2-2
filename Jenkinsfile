pipeline {
    agent any

    stages {
        stage("Check Branch") {
            when {
                expression {
                    env.BRANCH_NAME == 'main'
                }
            }
            steps {
                echo "Running on main branch"
            }
        }

        stage("Restore dependencies") {
            when {
                expression {
                    env.BRANCH_NAME == 'main'
                }
            }
            steps {
                bat "dotnet restore"
            }
        }

        stage("Build") {
            when {
                expression {
                    env.BRANCH_NAME == 'main'
                }
            }
            steps {
                bat "dotnet build --no-restore"
            }
        }

        stage("Test") {
            when {
                expression {
                    env.BRANCH_NAME == 'main'
                }
            }
            steps {
                bat "dotnet test --no-build --verbosity normal"
            }
        }
    }
}