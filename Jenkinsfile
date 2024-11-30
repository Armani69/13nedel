pipeline {
  agent any
  
  environment {
    DOCKER_REGISTRY = 'your-docker-registry'
  }
  
  stages {
      stage('Клонирование репозитория') {
          steps {
              git 'https://github.com/Armani69/13nedel.git'
            }
        }
    
        stage('Сборка Docker-образа') {
            steps {
                sh 'docker build -t sample-node-app:latest .'
            }
        }
    
        stage('Запуск контейнера внутри Jenkins') {
            steps {
                script {
                    docker.image('sample-node-app:latest').in
side {
                        sh 'echo "Запуск контейнера внутри ко
нтейнера Jenkins"'
                        sh 'npm start'
                    }
                }
            }
        }
    }
}
