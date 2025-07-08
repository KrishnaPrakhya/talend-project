pipeline {
    agent any

    environment {
        JAVA_HOME = "C:\\Program Files\\Java\\jdk-21"
    }

    parameters {
        string(name: 'CSV_FILE_PATH', defaultValue: 'C:\Users\nagak\OneDrive\Desktop\customers.csv')
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/KrishnaPrakhya/talend-project/'
            }
        }

        stage('Run Talend JAR Job') {
            steps {
                bat """
                java -jar CustomerLoggerJob_0.1.jar --context=Default ^
                --context_param CSV_FILE_PATH=%CSV_FILE_PATH%
                """
            }
        }
    }
}
