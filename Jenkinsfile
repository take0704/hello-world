JENKINS_SCRIPT_DIR="jenkins/sh/"

pipeline{ 
	agent any
	environment { 
		CI = 'true'
	}
	stages{
		stage('ビルド'){
			steps {
				sh "pwd"
				sh "ls -la"
				executeScript("${JENKINS_SCRIPT_DIR}test.sh","")
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
	parmittion_setting(script_filename)
	sh "${script_filename} ${args}"
}

//指定パスの実行権限を設定
def parmittion_setting(path){
	sh "chmod +x ${path}"
}

