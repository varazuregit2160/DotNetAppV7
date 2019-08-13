pipeline
{
	agent any
	
    stage('build and publish')
	{
		steps{
				bat 'dotnet publish "DotNetAppV7\\DotNetAppV7.sln" -c Release'
				echo "*************Publishing Completed**************"
			}
    }
    stage('Deploy')
    {
		steps{
				azureWebAppPublish azureCredentialsId: params.azure_cred,
				resourceGroup: params.res_name, appName: params.App_Name, sourceDirectory: "C:\\Program Files (x86)\\Jenkins\\workspace\\dotnetappv1 pipeline\\DotNetAppV1\\DotNetAppV1\\bin\\Release\\netcoreapp2.1\\publish"
				echo "****************Deployment Completed******************"
			}
    }
}
