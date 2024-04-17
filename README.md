# Azure_NodeJS_RunNpmPublish
Use this task to publish npm packages or to run an npm command. Supports npmjs.com and authenticated registries like Azure Artifacts. This Template used for publishing of npm package.

## Parameters:

The pipeline requires the following parameters to be defined:

| Name | type | Default | Required/Optional | Comments |
| :-------------: | :-------------: | ------------- | :-------------: | :-------------: |
| filePath | String | $(Build.SourcesDirectory) | Required | define the filepath or working directory for package.json. Youc can also pass arguements  if required |
| npmPublish | string | publish | Optional | used as per requirement that if you want to publish package or not |



These parameters provide multiple use case options for the template, enable/disable flags for the utilization of different templates as per the requirements.


## Use Cases

You can directly call a particular template as per the requirement. for example: 

  ```yaml
  # azure-pipeline.yml
  resources:
  repositories:
    - repository: Template
      type: github
      name: your_username/Azure_NodeJS_RunNpmPublish
      ref: <respective branch name>
      endpoint: 'githubServiceConnectioNname'

  steps:
  # passing the parameters
  - template: Azure_NodeJS_RunNpmPublish.yml
    parameters:
        filePath: ${{ parameters.filePath }} 
        npmPublish: ${{ parameters.npmPublish }}
        defaultBranch: ${{ parameters.defaultBranch }}
        
Make sure to adjust the repository name, branch name, and parameter values according to your project's requirements.

  ```
