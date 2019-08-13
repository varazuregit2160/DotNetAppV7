pipeline
{
	agent any
	stages
	{
    stage ('build and publish')
	{
		steps
			{
				bat 'dotnet publish "AppV7 Deploy with jenkinsfile\\DotNetAppV7.sln" -c Release'
				echo "*************Publishing Completed**************"
			}
    }
    stage ('Deploy')
    {
		steps
			{
				azureWebAppPublish azureCredentialsId: params.azure_cred,
				resourceGroup: params.res_name, appName: params.App_Name, sourceDirectory: "C:\\Program Files (x86)\\Jenkins\\workspace\\AppV7 Deploy with jenkinsfile\\DotNetAppV1\\DotNetAppV1\\bin\\Release\\netcoreapp2.1\\publish"
				echo "****************Deployment Completed******************"
			}
    }
	}
}
