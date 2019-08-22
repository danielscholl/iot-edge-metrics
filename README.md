# IoT Edge Metrics

These are Containers to be used for IoT Edge Metrics Gathering for Windows

### Build using Azure Pipelines

[![Build Status](https://dascholl.visualstudio.com/IoT/_apis/build/status/danielscholl.iot-edge-metrics?branchName=master)](https://dascholl.visualstudio.com/IoT/_build/latest?definitionId=44&branchName=master)


## Supported platforms 
Windows amd64

## Enable Metrics on the Edge
Metrics are enabled using the following methods found in [edge docs](https://github.com/Azure/iotedge/blob/master/doc/Metrics.md)


```powershell
# Deploy the Module
#----------------------------------
az iot edge set-modules `
    --device-id $Device `
    --hub-name $Hub `
    --content deployment.json
```

## Access the Edge Metrics
Metrics are available directly on the Edge Device  `http://edgedevice:8080`

![[0]][0]

[0]: ./diagrams/Dashboard.png "Dashboard"
