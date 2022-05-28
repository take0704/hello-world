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
					executeScript("test.sh")
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
def executeScript(script, args){

	add_execute_permission(script){
	sh ${script} ${args}
}

}
// 実行権限を追加
def add_execute_permission(path){
	sh "chmod +x ${path}"
}