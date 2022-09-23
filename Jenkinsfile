JENKINS_SCRIPT_DIR=jenkins/sh

pipeline{ 
	agent any
	environment { 
		CI = 'true'
	}
	stages{
		stage('ビルド'){
			steps {
				dir("${JENKINS_SCRIPT_DIR}") {
					sh "pwd"
					sh "ls -la"
					executeScript("test.sh","")
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

// スクリプトを実行
def executeScript(script_filename, args){
	sh "chmod +x ${WORKSPACE}/${JENKINS_SCRIPT_DIR}/${script_filename}"
	sh "${WORKSPACE}/${JENKINS_SCRIPT_DIR}/${script_filename} ${args}"
}



