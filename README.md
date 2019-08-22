# IoT Edge Metrics

These are Containers to be used for IoT Edge Metrics Gathering for Windows

### Build using Azure Pipelines

[![Build Status](https://dascholl.visualstudio.com/IoT/_apis/build/status/IoT-Docker%20container-CI?branchName=master)](https://dascholl.visualstudio.com/IoT/_build/latest?definitionId=42&branchName=master)


## Supported platforms 
Windows amd64

## Deploy the Module to the Edge Device

```powershell
# Deploy the Module
#----------------------------------
az iot edge set-modules `
    --device-id $Device `
    --hub-name $Hub `
    --content deployment.json
```

To utilize docker client on the windows server the docker host must be set properly for Moby.

```powershell
[Environment]::SetEnvironmentVariable("DOCKER_HOST", "npipe:////./pipe/iotedge_moby_engine")
```

## Access the Edge Metrics
Metrics are available directly on the Edge Device  `http://edgedevice:8080`

![[0]][0]
_Dashboard_

[0]: ./diagrams/Dashboard.png "Dashboard"