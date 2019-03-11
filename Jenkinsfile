node {
stage('checkout'){
checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'GIT_CRED1', url: 'https://github.com/amitavl/BankRepoMultiBranchPipe']]])
echo"checkout done"
}

stage('build')	{

bat '''
cd bank-mgmt-sys-python
python main.py

'''
}
stage('deploy-dev')	{
bat '''
cd bank-mgmt-sys-python
powershell.exe start main.py

'''
    }

}



