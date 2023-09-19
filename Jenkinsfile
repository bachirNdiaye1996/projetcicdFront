pipeline{
	agent any
	stages{
		stage("Clone the project") {
      steps{
        git branch: 'master', url: 'https://github.com/bachirNdiaye1996/projetcicdFront.git'
      }
    }
		stage('build'){
		    steps{
		        sh 'npm install --legacy-peer-deps'
				// sh "sed -i 's/module.exports = paginate;/export default paginate;/' ${WORKSPACE}/node_modules/jw-paginate/lib/jw-paginate.js"
				// sh "sed -i 's/export = paginate;/export default paginate;/' ${WORKSPACE}/node_modules/jw-paginate/lib/jw-paginate.d.ts"
		        sh 'ng build --configuration production'
		    }
		}
		stage('deploy'){
		    steps{
				sh 'sudo rm -rv /var/www/html/test'
				sh 'sudo mkdir -p /var/www/html/test'
				sh 'sudo cp -rv ./dist/projetcicdFront/* /var/www/html/test'
			}
		}
	}
}
