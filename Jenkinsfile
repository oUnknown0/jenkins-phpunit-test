pipeline {
    agent any

    stages {
        stage('Prepare Environment') {
            steps {
                script {
                    // Install Composer
                    sh 'curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer'
                }
            }
        }

        stage('Build') {
            steps {
                sh '/usr/local/bin/composer install'
            }
        }

        stage('Test') {
            steps {
                sh './vendor/bin/phpunit tests'
            }
        }
    }
}
