JENKINS_SCRIPT_DIR="./jenkins/sh"

pipeline{ 
	agent any
	environment { 
		CI = 'true'
	}
	stages{
		stage('ビルド'){
			steps {
				dir("${JENKINS_SCRIPT_DIR}") {
					bash "pwd"
					bash "ls -la"
					executeScript("test.sh","")
				}
			}
		}
	}
	post {
		always{
			// 
			bash 'echo "always"'
		}
		success {
			// 成功時のメッセージ
			bash 'echo "成功"'
		}
		failure {
			// 失敗時のメッセージ
			bash 'echo "失敗"'
		}
	}
}

// スクリプトを実行
def executeScript(script, args){
	bash "pwd"
	bash "ls -la"
	bash "chmod +x ${script}"
	bash "${script} ${args}"
}



