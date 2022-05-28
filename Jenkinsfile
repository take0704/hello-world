JENKINS_SCRIPT_DIR="./jenkins/sh"

pipeline{ 
	agent any
	environment { 
		CI = 'true'
    }
	stages{
		stage('ビルド'){
			steps {
				sh '${JENKINS_SCRIPT_DIR}/test.sh'
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
