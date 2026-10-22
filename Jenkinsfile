pipeline {
    agent {
        dockerfile {
            // build-env 디렉터리 안의 Dockerfile 지정
            filename 'Dockerfile'
            dir 'build-env'
            additionalBuildArgs '--build-arg NODE_ENV=development'
        }
    }

    stages {
        stage('Nginx Container Test') {
            steps {
                echo '=== Dockerfile로 빌드된 Nginx 컨테이너 내부입니다 ==='

                // 1. Nginx 버전 확인
                sh 'nginx -v'

                // 2. 전달된 환경변수(NODE_ENV) 확인
                sh 'echo "현재 NODE_ENV 환경변수: $NODE_ENV"'

                // 3. 컨테이너 내부 OS 및 호스트명 확인
                sh 'cat /etc/os-release | grep PRETTY_NAME'
                sh 'echo "컨테이너 ID (Hostname): $(hostname)"'
            }
        }
    }
}