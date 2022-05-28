JENKINS_SCRIPT_DIR="./jenkins/sh"

pipeline{ 
	environment { 
		CI = 'true'
    }
	stages{
		stage('ビルド'){
			steps {
				dir('${JENKINS_SCRIPT_DIR}') {
				    sh './test.sh'
				}
			}
		}
	}
    post {
		always{
			// 
			sh 'echo "always"'
		}
		success {
			// 成功時のメッセージ
			sh 'echo "成功"'
		}
		failure {
			// 失敗時のメッセージ
			sh 'echo "失敗"'
		}
	}
}
