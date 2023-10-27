---
page_type: sample
languages:
- nodejs
- javascript
products:
- azure
- azure-app-service
description: "This sample demonstrates a tiny Hello World Node.js app for Azure App Service."
---

# Node.js Hello World

This sample demonstrates a tiny Hello World node.js app for [App Service Web App](https://docs.microsoft.com/azure/app-service-web).

## Jenkinsfile

Simple Jenkinsfile for demo CI pipeline:
- Clone repo
- Build image
- Push image
Pipeline will call pre-defined pod template (labeled in `jenkins-docker`) to build/push image.

### Variable within build stage
| Name | Type | Description |
| -------- | -------- | -------- |
|  DOCKER_CREDENDITIAL  |  credential(username/password)  |  credential used to access dockerhub  |

## Contributing

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/). For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.

